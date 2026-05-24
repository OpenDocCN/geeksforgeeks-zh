# JavaFX Insets 类

> 原文: [https://www.geeksforgeeks.org/javafx-insets-class/](https://www.geeksforgeeks.org/javafx-insets-class/)

`Insets` 类是 JavaFX 的一部分。`Insets` 类存储矩形区域四条边的内部偏移量。`Insets` 类继承了 `java.lang.Object` 类。

## 类的构造函数

1.  `Insets(double a)`：为所有四个偏移构造一个具有相同值的新 `Insets` 实例。
2.  `Insets(double top, double right, double bottom, double left)`：用四个不同的偏移量构造一个新的 `Insets` 实例。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `equals(java.lang.Object obj)` | 指示某个其他对象是否“等于”这个对象。 |
| `getBottom()` | 返回底部的插图 |
| `getLeft()` | 返回左侧的插图 |
| `getRight()` | 返回右侧的插图 |
| `getTop()` | 返回顶部的插图 |
| `hashCode()` | 返回类的 hashcode |

## 程序示例

以下程序将说明 `Insets` 类的使用：

### 1. 创建两个 Insets 对象并显示内容

这个程序创建两个名为 `insets_1` 和 `insets_2` 的 `Insets` 对象。在调用构造函数时传入偏移量作为参数。我们将使用 `getTop()`、`getBottom()`、`getLeft()`、`getRight()` 方法获取 `Insets` 对象的四边偏移量并显示它们。

```java
// Java program to create two insets 
// object and display the contents
import javafx.geometry.Insets;

public class Insets_1 {

    // Main Method
    public static void main(String args[])
    {
        // create two insets object
        Insets insets_1 = new Insets(20.0f);
        Insets insets_2 = new Insets(20.0f, 40.0f, 60.0f, 70.0f);

        // display the insets
        display(insets_1);
        display(insets_2);
    }

    // display method
    public static void display(Insets insets)
    {
        double left, right, bottom, top;

        // get the insets
        left = insets.getLeft();
        right = insets.getRight();
        bottom = insets.getBottom();
        top = insets.getTop();

        // display the insets
        System.out.println("Insets of the object");
        System.out.println("Left= " + left + ", Right = " 
                           + right + ", Bottom = " + bottom 
                           + ", Top = " + top);
    }
}
```

**输出：**

```java
Insets of the object
Left = 20.0, Right = 20.0, Bottom = 20.0, Top = 20.0
Insets of the object
Left = 70.0, Right = 40.0, Bottom = 60.0, Top = 20.0
```

### 2. 创建三个 Insets 对象，显示内容并检查是否相等

这个程序创建三个名为 `insets_1`、`insets_2` 和 `insets_3` 的 `Insets` 对象。在调用构造函数时传入偏移量作为参数。我们将使用 `getTop()`、`getBottom()`、`getLeft()`、`getRight()` 方法获取 `Insets` 对象的四边偏移量并显示它们。我们还将使用 `equals` 方法检查这些 `Insets` 对象是否彼此相等。

```java
// Java program to create three objects of insets
// and display its contents and check whether 
// they are equal to each other or not
import javafx.geometry.Insets;

public class Insets_2 {

    // Main Method
    public static void main(String args[])
    {
        // create three insets objects
        Insets insets_1 = new Insets(120.0f, 150.0f,
                                      40.0f, 60.0f);

        Insets insets_2 = new Insets(120.0f, 150.0f, 
                                      40.0f, 60.0f);

        Insets insets_3 = new Insets(200.0f, 120.0f, 
                                      60.0f, 40.0f);

        // display the 3 insets
        display(insets_1);
        display(insets_2);
        display(insets_3);

        // check whether any insets is equal to other or not
        System.out.println("Insets 1 equals Insets 2 = " 
                           + insets_1.equals(insets_2));

        System.out.println("Insets 2 equals Insets 3 = " 
                            + insets_2.equals(insets_3));

        System.out.println("Insets 3 equals Insets 1 = " 
                            + insets_3.equals(insets_1));
    }

    // display Method
    public static void display(Insets insets)
    {
        double left, right, bottom, top;

        // get the insets
        left = insets.getLeft();
        right = insets.getRight();
        bottom = insets.getBottom();
        top = insets.getTop();

        // display the insets
        System.out.println("Insets of the object");
        System.out.println("Left= " + left + ", Right= "
                           + right + ", Bottom= " + bottom 
                           + ", Top = " + top);
    }
}
```

**输出：**

```java
Insets of the object
Left= 60.0, Right= 150.0, Bottom= 40.0, Top = 120.0
Insets of the object
Left= 60.0, Right= 150.0, Bottom= 40.0, Top = 120.0
Insets of the object
Left= 40.0, Right= 120.0, Bottom= 60.0, Top = 200.0
Insets 1 equals Insets 2 = true
Insets 2 equals Insets 3 = false
Insets 3 equals Insets 1 = false
```

**注意：** 上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考：** [https://docs.oracle.com/javafx/2/api/javafx/geometry/Insets.html](https://docs.oracle.com/javafx/2/api/javafx/geometry/Insets.html)