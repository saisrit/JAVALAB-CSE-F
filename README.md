# JAVALAB-CSE-F
EXPERIMENT-1
```java
1A>DISPLAY DEFAULT VALUES OF PRIMITIVE DATA TYPES IN JAVA
CODE:
class DefaultValues {
    byte b;
    short s;
    int i;
    long l;
    float f;
    double d;
    char c;
    boolean bool;
        public static void main(String[] args) {
        DefaultValues obj = new DefaultValues();
        System.out.println("Default byte value: " + obj.b);
        System.out.println("Default short value: " + obj.s);
        System.out.println("Default int value: " + obj.i);
        System.out.println("Default long value: " + obj.l);
        System.out.println("Default float value: " + obj.f);
        System.out.println("Default double value: " + obj.d);
        System.out.println("Default char value: '" + obj.c + "'");
        System.out.println("Default boolean value: " + obj.bool);
    }
}

```

##output
![output](ep1a.png)


``` java
1B>Program to find roots of a quadratic equation
CODE:
import java.util.Scanner;

class QuadraticRoots {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter coefficient a: ");
        double a = sc.nextDouble();

        System.out.print("Enter coefficient b: ");
        double b = sc.nextDouble();

        System.out.print("Enter coefficient c: ");
        double c = sc.nextDouble();

        double D = b * b - 4 * a * c;

        System.out.println("Discriminant = " + D);

        if (D > 0) {
            double x1 = (-b + Math.sqrt(D)) / (2 * a);
            double x2 = (-b - Math.sqrt(D)) / (2 * a);
            System.out.println("Roots are real and distinct");
            System.out.println("Root 1 = " + x1);
            System.out.println("Root 2 = " + x2);
        } 
        else if (D == 0) {
            double x = -b / (2 * a);
            System.out.println("Roots are real and equal");
            System.out.println("Root = " + x);
        } 
        else {
            double real = -b / (2 * a);
            double imag = Math.sqrt(-D) / (2 * a);
            System.out.println("Roots are imaginary");
            System.out.println("Root 1 = " + real + " + " + imag + "i");
            System.out.println("Root 2 = " + real + " - " + imag + "i");
        }

        sc.close();
    }
}


```
##output
![output](ep1b.png)


EXPERIMENT 2
```java
2A)Implement class mechanism in Java. Create a class, methods and invoke 
them inside main method.

CODE:
class MyClass {
   void displayMessage() {
        System.out.println("Hello! I am supreeth.");
    }
    int add(int a, int b) {
        return a + b;
    }
}
public class Mainclass {
    public static void main(String[] args) {
MyClass obj = new MyClass();
        obj.displayMessage();
        int result = obj.add(15, 30);
        System.out.println("Addition Result: " + result);
    }
}
```
##output
![output](ep2a.png)

```
2B) program implement method overloading.
CODE:
class Overload{

    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }


    int add(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        Overload obj = new Overload();

        int result1 = obj.add(15, 50);
        double result2 = obj.add(10.5, 40.5);
        int result3 = obj.add(25,45,60);

        System.out.println("result of adding two integers: " + result1);
        System.out.println("result of adding two doubles values : " + result2);
        System.out.println("result of adding three integers: " + result3);
    }
}



```

##output
![output](eb2b.png)



```
2c)program to implement constructor.
CODE:
class Student {
    String name;
    int age;
    int marks;

    Student(String n, int a, int m) {
        name = n;
        age = a;
        marks = m;
    }


    void display() {
        System.out.println("Name  : " + name);
        System.out.println("Age   : " + age);
        System.out.println("Marks : " + marks);
    }


    public static void main(String[] args) {
        Student s = new Student("Supreeth", 19, 85);
        s.display();
    }
}

```
##output
![output](ep2c.png)
