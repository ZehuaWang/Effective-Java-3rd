# Effective-Java-3rd

## Item 1: Facotry Methods

Consider static factory method instead of construcotrs

Java allows constructor overloading -> based on the type of the parameters

Limitation of constructors: You can not overload based on the name of parameters

Static factory methods can help by providing purposeful naming.

Example: Creating a Point(x,y) class

````
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
````

Use Static factory method -> of(), valueOf()

![image](https://user-images.githubusercontent.com/40006814/160308585-9d409a04-e502-4eb5-b478-a71b362c4513.png)

![image](https://user-images.githubusercontent.com/40006814/160309722-5c563203-abaf-4d30-be0b-5fc687626838.png)

````
// can not be inherited
public class Point {
    double x, y;

    private Point(double x, double y) {
        this.x = x;
        this.y = y;
    }

    private Point(double rho, double phi, int dummy) {
        this.x = rho * Math.cos(phi);
        this.y = rho * Math.sin(phi);
    }

    // in java, we can not use "var" for return types
    // make the method name informative
    public static Point fromCartesian(double x, double y) {
        return new Point(x, y);
    }

    public static Point fromPolar(double x, double y) {
        return new Point(x, y, 0);
    }
}
````

## Item 2: Builders

![image](https://user-images.githubusercontent.com/40006814/160936364-5952881b-15db-4ff6-a18e-93e6d7607606.png)

![image](https://user-images.githubusercontent.com/40006814/160937801-c54c3175-7f45-4a39-8def-1446140690e3.png)

