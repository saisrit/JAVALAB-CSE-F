
9a>Write a java program that connects to a database using JDBC
```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class Create {

    public static void main(String[] args) {

        // Database credentials
        String url = "jdbc:mysql://localhost:3306/supreeth";
        String username = "root";
        String password = "Pass@word";   // Change as per your MySQL password

        try {
            // Step 1: Load JDBC Driver (Optional in latest versions)
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Step 2: Establish Connection
            Connection con = DriverManager.getConnection(url, username, password);

            // Step 3: Create Statement Object
            Statement stmt = con.createStatement();

            // Step 4: Create Table SQL Query
            String query = "CREATE TABLE students ("
                    + "id INT PRIMARY KEY AUTO_INCREMENT, "
                    + "name VARCHAR(50), "
                    + "age INT, "
                    + "course VARCHAR(50))";

            // Step 5: Execute Query
            stmt.execute(query);

            System.out.println("Table created successfully!");

            // Step 6: Close connection
            stmt.close();
            con.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}


```


##output
![output](ep9a.png)




9b>Write a java program to connect to a database using JDBC and insert values
into it.
```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class Insert {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/supreeth";
        String username = "root";
        String password = "Pass@word";   // Change to your MySQL password

        try {
            // Load Driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish Connection
            Connection con = DriverManager.getConnection(url, username, password);

            // Create Statement
            Statement stmt = con.createStatement();

            // Insert 10 records in single query
            String query = "INSERT INTO students (name, age, course) VALUES "
                    + "('Rahul', 20, 'Computer Science'),"
                    + "('Anjali', 19, 'Information Technology'),"
                    + "('Vikram', 21, 'Electronics'),"
                    + "('Sneha', 20, 'Mechanical'),"
                    + "('Arjun', 22, 'Civil'),"
                    + "('Priya', 19, 'Computer Science'),"
                    + "('Kiran', 21, 'Electrical'),"
                    + "('Meena', 20, 'Information Technology'),"
                    + "('Rohit', 22, 'Mechanical'),"
                    + "('Divya', 18, 'Computer Science')";

            // Execute Query
            int rows = stmt.executeUpdate(query);

            System.out.println(rows + " records inserted successfully!");

            // Close Connection
            stmt.close();
            con.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}



```

##output
![output](ep9b.png)






9c>Write a java program to connect to a database using JDBC and delete values
from it.
```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class DeleteStudent {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/supreeth";
        String username = "root";
        String password = "Pass@word";   // Change accordingly

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");

            Connection con = DriverManager.getConnection(url, username, password);

            Statement stmt = con.createStatement();

            String query = "DELETE FROM students WHERE id=5";

            int rows = stmt.executeUpdate(query);

            System.out.println(rows + " record(s) deleted successfully!");

            stmt.close();
            con.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}




```



##output
![output](ep9c.png)










