# JavaFX InnerShadow 类

> 原文: [https://www.geeksforgeeks.org/javafx-innershadow-class/](https://www.geeksforgeeks.org/javafx-innershadow-class/)

`InnerShadow` 类是 JavaFX 的一部分。`InnerShadow` 类创建一个高级效果，以给定的指定半径、偏移、扼流、颜色和模糊类型在对象的边缘内部呈现阴影。`InnerShadow` 类继承了 `Effect` 类。

## 类的构造函数

1.  `InnerShadow()`: 创建一个新的内阴影对象。
2.  `InnerShadow(BlurType blurType, Color color, double radius, double choke, double offsetX, double offsetY)`: 用指定的模糊类型、颜色、半径、扼流和偏移创建一个新的内阴影对象。
3.  `InnerShadow(double r, Color c)`: 用指定的半径和颜色创建一个新的内阴影对象。
4.  `InnerShadow(double radius, double offsetX, double offsetY, Color color)`: 用指定的半径、偏移量和颜色创建一个新的内阴影对象。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `getBlurType()` | 返回效果的模糊类型。 |
| `setBlurType(BlurType v)` | 设置效果的模糊类型。 |
| `getChoke()` | 返回属性 choke 的值。 |
| `setChoke(double d)` | 设置属性 choke 的值。 |
| `setColor(Color v)` | 设置效果的颜色。 |
| `getColor()` | 返回效果的颜色。 |
| `setInput(Effect v)` | 设置属性输入的值。 |
| `getInput()` | 返回属性输入的值。 |
| `setOffsetX(double v)` | 设置效果的偏移值。 |
| `setOffsetY(double v)` | 设置效果的偏移值。 |
| `getOffsetX()` | 返回效果的 X 偏移值。 |
| `getOffsetY()` | 返回效果的 Y 偏移值。 |
| `setRadius(double v)` | 设置效果的半径值。 |
| `getRadius()` | 返回效果的半径值。 |

## 程序示例

下面的程序说明了 `InnerShadow` 类的使用。

### 示例 1：创建一个圆并添加 InnerShadow 效果

在这个程序中我们将创建一个名为 `circle` 的圆，并创建一个具有指定半径和颜色的 `InnerShadow` 效果 `sepia_tone`。使用 `setEffect()` 方法将 `InnerShadow` 效果添加到圆中，圆将被添加到 `Group` 中。使用 `setTranslateX()` 和 `setTranslateY()` 方法将圆圈平移到舞台中的特定位置。`Group` 将被添加到 `Scene` 中，场景将被添加到 `Stage` 中。

```java
// Java program to create a Circle
// and add InnerShadow effect to it
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;
import javafx.scene.image.*;
import javafx.scene.effect.*;
import java.io.*;
import javafx.scene.shape.Circle;
import javafx.scene.paint.Color;
import javafx.scene.Group;

public class Inner_shadow_1 extends Application {

    // launch the application
    public void start(Stage stage) throws Exception
    {
        // set title for the stage
        stage.setTitle("Inner_shadow example");

        // create a circle
        Circle circle = new Circle(50.0f, 50.0f, 50.0f);

        // set fill for circle
        circle.setFill(Color.BLUE);

        // translate to a position
        circle.setTranslateX(50.0f);
        circle.setTranslateY(50.0f);

        // create a sepia_tone effect
        InnerShadow sepia_tone = new InnerShadow(10, Color.RED);

        // set effect
        circle.setEffect(sepia_tone);

        // create a Group
        Group group = new Group(circle);

        // create a scene
        Scene scene = new Scene(group, 200, 200);

        // set the scene
        stage.setScene(scene);

        stage.show();
    }

    // Main Method
    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```

**输出:**

![](img/51dcc17cc3dad886a77d2fc6de3cf7dc.png)

### 示例 2：创建四个圆并添加不同的 InnerShadow 效果

在本程序中，我们将创建名为 `circle`、`circle1`、`circle2`、`circle3` 的圆以及名为 `Inner_shadow1`、`Inner_shadow2`、`Inner_shadow3`、`Inner_shadow4` 的 `InnerShadow` 效果。使用 `setEffect()` 方法将内阴影效果添加到圆圈中，圆圈将被添加到 `Group` 中。使用 `setTranslateX()` 和 `setTranslateY()` 方法，圆圈将被转换到舞台中的特定位置。`Group` 将被添加到 `Scene` 中，场景将被添加到 `Stage` 中。

```java
// Java program to create four Circles and add
// InnerShadow effect to it which are of different
// blur types and different values of choke,
// offsetX, offsetY and radius
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;
import javafx.scene.image.*;
import javafx.scene.effect.*;
import java.io.*;
import javafx.scene.shape.Circle;
import javafx.scene.paint.Color;
import javafx.scene.Group;

public class Inner_shadow_2 extends Application {

    // launch the application
    public void start(Stage stage) throws Exception
    {
        // set title for the stage
        stage.setTitle("Inner_shadow example");

        // create circles
        Circle circle = new Circle(0.0f, 0.0f, 25.0f, Color.RED);
        Circle circle1 = new Circle(0.0f, 0.0f, 25.0f, Color.RED);
        Circle circle2 = new Circle(0.0f, 0.0f, 25.0f, Color.RED);
        Circle circle3 = new Circle(0.0f, 0.0f, 25.0f, Color.RED);

        // translate to positions
        circle.setTranslateX(50.0f);
        circle.setTranslateY(50.0f);
        circle1.setTranslateX(150.0f);
        circle1.setTranslateY(50.0f);
        circle2.setTranslateX(50.0f);
        circle2.setTranslateY(150.0f);
        circle3.setTranslateX(150.0f);
        circle3.setTranslateY(150.0f);

        // create Inner_shadow effects
        InnerShadow Inner_shadow1 = new InnerShadow(BlurType.values()[0],
                                       Color.BLACK, 5, 3.0f, 2.0f, 2.0f);
        InnerShadow Inner_shadow2 = new InnerShadow(BlurType.values()[1],
                                       Color.BLACK, 5, 3.0f, 3.0f, 3.0f);
        InnerShadow Inner_shadow3 = new InnerShadow(BlurType.values()[2],
                                       Color.BLACK, 5, 4.0f, 3.0f, 3.0f);
        InnerShadow Inner_shadow4 = new InnerShadow(BlurType.values()[3],
                                       Color.BLACK, 5, 4.0f, 2.0f, 2.0f);

        // set effects
        circle.setEffect(Inner_shadow1);
        circle1.setEffect(Inner_shadow2);
        circle2.setEffect(Inner_shadow3);
        circle3.setEffect(Inner_shadow4);

        // create a Group
        Group group = new Group(circle, circle1, circle2, circle3);

        // create a scene
        Scene scene = new Scene(group, 400, 400);

        // set the scene
        stage.setScene(scene);

        stage.show();
    }

    // Main Method
    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```

**输出:**

![](img/8489d2df63641c8d421eba8544ceda0a.png)

**注意:** 上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:** [https://docs.oracle.com/javase/8/javafx/api/javafx/scene/effect/InnerShadow.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/effect/InnerShadow.html)