# JavaFX `Rectangle2D` 类

> 原文: [https://www.geeksforgeeks.org/javafx-rectangle2d-class/](https://www.geeksforgeeks.org/javafx-rectangle2d-class/)

`Rectangle2D` 类是 JavaFX 的一部分。`Rectangle2D` 类使用矩形左上角的给定坐标以及宽度和高度创建一个矩形，或者由位置(`minX`，`minY`)和尺寸(宽度 x 高度)定义。

## 类的构造函数

*   `Rectangle2D(double minX, double minY, double width, double height)`: 用指定的宽度高度和矩形左上角的坐标创建一个新的 `Rectangle2D`。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `contains(double x, double y)` | 检查指定的坐标是否在矩形 2D 的边界内。 |
| `contains(double x, double y, double w, double h)` | 检查指定的矩形是否位于给定的矩形内。 |
| `contains(Point2D p)` | 检查指定的 `Point2D` 坐标是否在矩形 2D 的边界内。 |
| `contains(Rectangle2D r)` | 检查指定的矩形是否位于给定的矩形内。 |
| `getHeight()` | 返回矩形的高度。 |
| `getWidth()` | 返回矩形的宽度。 |
| `getMaxX()` | 此矩形 2D 右下角的 x 坐标。 |
| `getMinX()` | 此矩形 2D 左上角的 x 坐标。 |
| `getMaxY()` | 此矩形 2D 右下角的 y 坐标。 |
| `getMinY()` | 此矩形 2D 左上角的 y 坐标。 |
| `intersects(double x, double y, double w, double h)` | 检查指定的矩形是否与矩形 2D 对象相交。 |
| `intersects(Rectangle2D r)` | 检查指定的矩形 2D 是否与矩形 2D 对象相交。 |

下面的程序说明了 `Rectangle2D` 类的使用：

### 1. 创建 `Rectangle2D` 对象并显示其详情，检查是否包含一个点以及是否与另一个矩形相交

此程序创建一个名为 `rectangle` 的 `Rectangle2D` 对象，参数为 `minX`、`minY`、`height` 和 `width`。使用 `display` 函数显示 `Rectangle2D` 对象的详情。`display` 函数使用 `getMinX()`、`getMinY()`、`getMaxX()`、`getMaxY()`、`getHeight()` 和 `getWidth()` 函数显示矩形的左上角坐标、右下角坐标及其宽度和高度。我们将使用 `contains()` 函数查看矩形是否包含一个点，并使用 `intersects` 函数检查它是否与另一个矩形相交，然后显示结果。

```java
// Java Program to create an object of
// Rectangle2D and display its details
// and whether it contains a point and
// whether it intersects a rectangle or not
import javafx.geometry.*;
import java.util.*;

class Rectangle_1 {

    // Main Method
    public static void main(String args[])
    {
        try {

            // rectangle object
            Rectangle2D rectangle = new Rectangle2D(100, 100,
                                                    100, 100);

            // display the rectangle
            display(rectangle);

            // Check whether the rectangle contains a point
            System.out.println("The rectangle contains point 150, 150 = "
                            + rectangle.contains(new Point2D(150, 150)));

            System.out.println("The rectangle contains point 50, 50 = "
                            + rectangle.contains(new Point2D(50, 50)));

            // Check Whether the rectangle
            // intersects another rectangle
            System.out.print("The rectangle intersects another rectangle "
                +"with width = 100, height = 100, minX = 50, & minY = 50: "
                            + rectangle.intersects(50, 50, 100, 100));
        }

        catch (Exception e)
        {
            System.err.println(e.getMessage());
        }
    }

    // display function
    public static void display(Rectangle2D rectangle)
    {

        // display the details of a rectangle
        System.out.println("Upper left point of the rectangle is = "
                 + rectangle.getMinX() + ", " + rectangle.getMinY());

        System.out.println("Lower right point of the rectangle is = "
                 + rectangle.getMaxX() + ", " + rectangle.getMaxY());

        System.out.println("Width and Height of the rectangle is = "
                + rectangle.getWidth() + ", " + rectangle.getHeight());
    }
}
```

**输出:**

> 矩形的左上角点为= 100.0，100.0
> 矩形的右下角点为= 200.0，200.0
> 矩形的宽度和高度为= 100.0，100.0
> 矩形包含点 150，150 =真
> 矩形包含点 50，50 =假
> 矩形与另一个矩形相交，宽度= 100，高度= 100，minX = 50，&minY = 0

### 2. 创建两个 `Rectangle2D` 对象并显示其详情，检查它们是否相交

此程序创建两个 `Rectangle2D` 对象，分别名为 `rectangle_1` 和 `rectangle_2`，参数为 `minX`、`minY`、`height` 和 `width`。使用 `display` 函数显示 `Rectangle2D` 对象的详情。`display` 函数使用 `getMinX()`、`getMinY()`、`getMaxX()`、`getMaxY()`、`getHeight()` 和 `getWidth()` 函数显示矩形的左上角坐标、右下角坐标及其宽度和高度。我们将使用 `intersects` 函数检查它是否与另一个矩形相交，然后显示结果。

```java
// Java Program to create two objects of
// Rectangle2D and display its details and
// check whether it intersects each other or not
import javafx.geometry.*;
import java.util.*;

class Rectangle_1 {

    // Main Method
    public static void main(String args[])
    {
        try
        {

            // rectangle object
            Rectangle2D rectangle_1 = new Rectangle2D(100, 100,
                                                      100, 100);

            Rectangle2D rectangle_2 = new Rectangle2D(100, 100,
                                                      100, 100);

            // display the rectangle details
            System.out.println("Rectangle_1 details");
            display(rectangle_1);

            System.out.println("");

            System.out.println("Rectangle_2 details");
            display(rectangle_2);

            // display whether these two
            // rectangle intersects or not
            System.out.println("These two rectangles intersect = "
                           + rectangle_1.intersects(rectangle_2));
        }

        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }

    // display method
    public static void display(Rectangle2D r)
    {

        // display the details of a rectangle
        System.out.println("Upper left point of the rectangle is = "
                                + r.getMinX() + ", " + r.getMinY());

        System.out.println("Lower right point of the rectangle is = "
                                + r.getMaxX() + ", " + r.getMaxY());

        System.out.println("Width and Height of the rectangle is = "
                            + r.getWidth() + ", " + r.getHeight());
    }
}
```

**输出:**

> 矩形 _1 详情
> 矩形的左上点为= 100.0，100.0
> 矩形的右下点为= 200.0，200.0
> 矩形的宽度和高度为= 100.0，100.0
>
> 矩形 _2 详情
> 矩形左上角点为= 100.0，100.0
> 矩形右下角点为= 200.0，200.0
> 矩形的宽度和高度为= 100.0，100.0
> 这两个矩形相交=真

**注意:** 上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:** [https://docs.oracle.com/javase/8/javafx/api/javafx/geometry/Rectangle2D.html](https://docs.oracle.com/javase/8/javafx/api/javafx/geometry/Rectangle2D.html)