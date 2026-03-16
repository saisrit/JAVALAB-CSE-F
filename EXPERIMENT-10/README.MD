10a>
```

```







10b>
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

