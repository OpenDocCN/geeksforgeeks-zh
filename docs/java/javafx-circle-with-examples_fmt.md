# JavaFX | 用例子圈出

> 原文: [https://www.geeksforgeeks.org/javafx-circle-with-examples/](https://www.geeksforgeeks.org/javafx-circle-with-examples/)

## Circle类概述

`Circle`类是JavaFX库的一部分。`Circle`类创建一个圆，该圆具有指定的圆心x和y位置、指定的圆半径和指定的填充。以像素为单位测量圆的半径和圆心。

## 构造函数

类的构造函数有：

1.  `Circle()`: 创建圆形的空实例。
2.  `Circle(double r)`: 创建一个指定半径的圆。
3.  `Circle(double X, double Y, double r)`: 用给定的圆心X和Y坐标，以及半径，创建一个圆。
4.  `Circle(double r, Paint f)`: 创建一个指定半径的圆并填充。
5.  `Circle(double X, double Y, double r, Paint f)`: 用给定的圆心X和Y坐标、半径以及指定的填充创建一个圆。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `getCenterX()` | 返回圆心的x坐标 |
| `getCenterY()` | 返回圆心的y坐标 |
| `getRadius()` | 返回圆的半径 |
| `setCenterX(double c)` | 设置圆心的x坐标 |
| `setCenterY(double c)` | 设置圆心的y坐标 |
| `setRadius(double c)` | 设置圆的半径 |
| `setFill(Paint p)` | 设置圆的填充 |

## 示例程序

以下程序说明了`Circle`类的使用：

### 1. 通过构造函数参数创建圆

Java program to create a circle by passing the coordinates of the center and radius as arguments in constructor: This program creates a Circle indicated by the name circle( the coordinates of the center and the radius is passed as arguments). The Circle will be created inside a scene, which in turn will be hosted inside a stage. The function setTitle() is used to provide title to the stage. Then a Group is created, and the circle is attached. The group is attached to the scene. Finally, the show() method is called to display the final results.

```java
// Java program to create circle by passing the
// coordinates of the center and radius
// as arguments in constructor
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.*;
import javafx.event.ActionEvent;
import javafx.scene.shape.Circle;
import javafx.scene.control.*;
import javafx.stage.Stage;
import javafx.scene.Group;

public class circle_0 extends Application {

    // launch the application
    public void start(Stage stage) {
        // set title for the stage
        stage.setTitle("creating circle");

        // create a circle
        Circle circle = new Circle(150.0f, 150.0f, 80.f);

        // create a Group
        Group group = new Group(circle);

        // create a scene
        Scene scene = new Scene(group, 500, 300);

        // set the scene
        stage.setScene(scene);

        stage.show();
    }

    public static void main(String args[]) {
        // launch the application
        launch(args);
    }
}
```

**输出:**
![](img/fb1b1c4e1029aeb1af09a8c52517168b.png)

### 2. 使用setter方法创建圆

Java program to create a circle and using the functions setCenterX, setCenterY and setRadius to set the coordinates of center and radius: This program creates a Circle indicated by the name circle. The coordinates for the center and the radius of the circle is set using setCenterX(), setCenterY(), and setRadius function. The Circle will be created inside a scene, which in turn will be hosted inside a stage. The function setTitle() is used to provide title to the stage. Then a Group is created, and the circle is attached. The group is attached to the scene. Finally, the show() method is called to display the final results.

```java
// Java program to create a circle and using
// the functions setCenterX, setCenterY and setRadius
// to set the coordinates of center and radius
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.*;
import javafx.event.ActionEvent;
import javafx.scene.shape.Circle;
import javafx.scene.control.*;
import javafx.stage.Stage;
import javafx.scene.Group;

public class circle_1 extends Application {

    // launch the application
    public void start(Stage stage) {
        // set title for the stage
        stage.setTitle("creating circle");

        // create a circle
        Circle circle = new Circle();

        // set the position of center of the circle
        circle.setCenterX(100.0f);
        circle.setCenterY(100.0f);

        // set Radius of the circle
        circle.setRadius(50.0f);

        // create a Group
        Group group = new Group(circle);

        // create a scene
        Scene scene = new Scene(group, 500, 300);

        // set the scene
        stage.setScene(scene);

        stage.show();
    }

    public static void main(String args[]) {
        // launch the application
        launch(args);
    }
}
```

**输出:**
![](img/1332c8a842e3e9baf039b023c7120142.png)

### 3. 创建指定半径、圆心和填充的圆

Java program to create a circle with specified radius and coordinates of center and also specified fill: This program creates a Circle indicated by the name circle.The coordinates for the center and the radius of the circle is set using setCenterX(), setCenterY(), and setRadius function. .The function set Fill() is used to set the fill of the circle The Circle will be created inside a scene, which in turn will be hosted inside a stage. The function setTitle() is used to provide title to the stage. Then a Group is created, and the circle is attached.The group is attached to the scene. Finally, the show() method is called to display the final results.

```java
// Java program to create a circle with specified
// radius and coordinates of center and also specified fill
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.*;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.scene.control.*;
import javafx.stage.Stage;
import javafx.scene.Group;

public class circle_2 extends Application {

    // launch the application
    public void start(Stage stage) {
        // set title for the stage
        stage.setTitle("creating circle");

        // create a circle
        Circle circle = new Circle();

        // set the position of center of the circle
        circle.setCenterX(100.0f);
        circle.setCenterY(100.0f);

        // set Radius of the circle
        circle.setRadius(50.0f);

        // set the fill of the circle
        circle.setFill(Color.BLUE);

        // create a Group
        Group group = new Group(circle);

        // create a scene
        Scene scene = new Scene(group, 500, 300);

        // set the scene
        stage.setScene(scene);

        stage.show();
    }

    public static void main(String args[]) {
        // launch the application
        launch(args);
    }
}
```

**输出:**
![](img/ee2e41b5e86a4ce0c8194b5ad761b543.png)

**注意:** 上述程序可能无法在联机IDE中运行，请使用脱机编译器。

**参考:** [https://docs.oracle.com/javafx/2/api/javafx/scene/shape/Circle.html](https://docs.oracle.com/javafx/2/api/javafx/scene/shape/Circle.html)