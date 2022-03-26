# Effective-Java-3rd

## Item 1: Facotry Methods

Consider static factory method instead of construcotrs

Java allows constructor overloading -> based on the type of the parameters

Limitation of constructors: You can not overload based on the name of parameters

Static factory methods can help by providing purposeful naming.

Example: Creating a Point(x,y) class

````
```
public class Point {
    double x, y;

    public Point(double x, double y) {
        this.x = x;
        this.y = y;
    }

    // wrong
    public Point(double rho, double phi) {
        this.x = rho * Math.cos(phi);
        this. y = rho * Math.sin(phi);
    }
}
```
````
