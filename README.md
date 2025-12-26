# JAVALAB-CSE-F
EXPERIMENT-1
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

OUTPUT:
Default byte value: 0
Default short value: 0
Default int value: 0
Default long value: 0
Default float value: 0.0
Default double value: 0.0
Default char value: ' '
Default boolean value: false



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

OUTPUT:
Enter coefficient a: 2
Enter coefficient b: 3
Enter coefficient c: -1
Discriminant = 17.0
Roots are real and distinct
Root 1 = 0.28077640640441515
Root 2 = -1.7807764064044151

Enter coefficient a: 1
Enter coefficient b: 1
Enter coefficient c: 1
Discriminant = -3.0
Roots are imaginary
Root 1 = -0.5 + 0.8660254037844386i
Root 2 = -0.5 - 0.8660254037844386i

$ java QuadraticRoot.java
Enter coefficient a: 1
Enter coefficient b: 4
Enter coefficient c: 4
Discriminant = 0.0
Roots are real and equal
Root = -2.0





