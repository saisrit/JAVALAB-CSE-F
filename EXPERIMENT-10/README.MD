10a>Without writing any code, build a GUI that display text in label and image in an Image View (use JavaFX).
```
 Steps to  Build GUL:

1. Open Scene Builder.
2. Select a new FXML document for designing the GUI.
3. Select a VBox Layout Container as the root element to arrange components vertically.
4. Set the alignment of the VBox to CENTER so that all components appear in the center.
5. Set the spacing between the components (for example 10px) to maintain proper distance.
6. Add padding around the VBox edges to provide spacing from the window edges.
7. Drag and place a Label component inside the VBox.
8. Set the text property of the Label (example: “Welcome to JavaFX”).
9. Adjust the font size and style of the Label to make the text clear and visible.
10. Drag and place an ImageView component below the Label inside the VBox.
11. Select an image file from the project resources folder and assign it to the ImageView.
12. Set the fitWidth and fitHeight properties of the ImageView to control the image size.
13. Enable Preserve Ratio = true so the image keeps its original proportions.
14. Enable Smooth = true to improve the image scaling quality.
15. Preview the layout in Scene Builder to ensure the text and image are displayed correctly.
16. Save the FXML file and image resource in the project folder.



```
output: 

<?xml version = "1.0" encoding = "UTF-8" ?>
<?import javafx.geometry.Insets ?>
<?import javafx.scene.control.Label ?>
<?import javafx.scene.image.Image ?>
<?import javafx.scene.image.ImageView ?>
<?import javafx.scene.layout.VBox ?>
<?import javafx.scene.text.Font ?>
<VBox alignment = "CENTER" spacing = "10" xmlns:fx = "http://javafx.com">
    <padding>
        <Insets top = "10" right = "10" bottom = "10" left = "10" />
    </padding>

    <!-- Label to display text -->
    <Label text = "Welcome to JavaFX" wrapText = "true">
        <font>
            <Font size = "20" />
        </font>
    </Label>
    <!-- ImageView to display image -->
    <ImageView fitWidth = "400" fitHeight = "300" preserveRatio = "true" smooth = "true">
        <image>
            <Image url = "@Screenshot 1-20(70).png" />
        </image>
    </ImageView>
</VBox>




10b>Build a Tip Calculator app using several JavaFX components and
learn how to respond to user interactions with the GUI.
```
//package com.tipcalculator;

import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;

public class TipCalculator extends Application {
    @Override
    public void start(Stage primaryStage) {
        // Create the input fields
        TextField priceField = new TextField();
        TextField tipPercentField = new TextField();
        Label resultLabel = new Label();
        
        // Create the calculate button
        Button calculateButton = new Button("Calculate");
        calculateButton.setOnAction(e -> {
            try {
                double price = Double.parseDouble(priceField.getText());
                double tipPercent = Double.parseDouble(tipPercentField.getText());
                if (price < 0 || tipPercent < 0) {
                    resultLabel.setText("Please enter positive values.");
                } else {
                    double tipAmount = price * tipPercent / 100; double totalAmount = price + tipAmount; 
                    resultLabel.setText("Tip: Rs" + String.format("%.2f", tipAmount) + ", Total: Rs" + String.format("%.2f", 
                    totalAmount));
                }
            } catch (NumberFormatException ex) {
                resultLabel.setText("Please enter valid numbers.");
            }
        });

        // Set up the layout
        GridPane grid = new GridPane();
        grid.setPadding(new Insets(10, 10, 10, 10));
        grid.setVgap(10);
        grid.setHgap(10);

        grid.add(new Label("Price (Rs):"), 0, 0);
        grid.add(priceField, 1, 0);
        grid.add(new Label("Tip %:"), 0, 1);
        grid.add(tipPercentField, 1, 1);
        grid.add(calculateButton, 1, 2);
        grid.add(resultLabel, 1, 3);

        // Create the scene and display the stage
        Scene scene = new Scene(grid, 300, 200);
        primaryStage.setTitle("Tip Calculator");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}


```

