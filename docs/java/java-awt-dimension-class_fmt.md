# Java AWT | `Dimension` 类

> 原文：[`https://www.geeksforgeeks.org/java-awt-dimension-class/`](https://www.geeksforgeeks.org/java-awt-dimension-class/)

`Dimension` 类是 Java AWT 的一部分。它以整数和双精度形式包含组件的高度和宽度。`Dimension` 类的用途是 Java AWT 和 Swing 的很多函数都返回 `Dimension` 对象。

**`Dimension` 类的构造函数**

1.  `Dimension()`：它将创建一个高度和宽度设置为零的新对象。
2.  `Dimension(Dimension d)`：它将创建一个与指定对象具有相同高度和宽度的新对象。
3.  `Dimension(int w, int h)`：会创建一个指定高度和宽度的新对象。

**`Dimension` 类的方法**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| `equals(Object o)` | 检查两个 `Dimension` 对象是否相等。 |
| `getHeight()` | 返回 `Dimension` 对象的高度 |
| `getWidth()` | 返回 `Dimension` 对象的宽度 |
| `getSize()` | 返回 `Dimension` 对象的大小。 |
| `hashCode()` | 返回 `Dimension` 的 hashcode。 |
| `setSize(Dimension d)` | 将对象的大小设置为指定的尺寸 |
| `setSize(double width, double height)` | 将高度和宽度设置为指定的双精度值 |
| `setSize(int width, int height)` | 将高度和宽度设置为指定的整数值 |

</figure>

**以下程序说明了 `Dimension` 类**：

### 程序示例：显示 `Dimension` 类（整数精度）功能

```java
// Java Program to show the functions
// of dimension class(Integer precision)
import java.awt.*;
class dimen {

// Main Method
    public static void main(String args[])
    {

// create dimension
        Dimension d = new Dimension();
        Dimension d1 = new Dimension(20, 30);
        Dimension d2 = new Dimension(d1);

// set height and width of dimension d
        d.setSize(30, 30);

// equating dimensions
        System.out.println("Dimension d and d1 " +
                    "are equal = " + d.equals(d1));

        System.out.println("Dimension d and d1 " +
                    "are equal = " + d1.equals(d2));

// print hashcode
        System.out.println("Hashcode of Dimension " +
                            "d = " + d.hashCode());

// display dimension
        display(d, "Dimension d");
        display(d1, "Dimension d1");
        display(d2, "Dimension d2");
    }

// display dimension
    public static void display(Dimension d, String s)
    {
        System.out.println(s +" Height = " + d.getHeight() +
                                " Width= " + d.getWidth());
    }
}
```

**输出**

```java
Dimension d and d1 are equal = false
Dimension d and d1 are equal = true
Hashcode of Dimension d = 1860
Dimension d Height = 30.0 Width= 30.0
Dimension d1 Height = 30.0 Width= 20.0
Dimension d2 Height = 30.0 Width= 20.0
```

### 程序示例：显示 `Dimension` 类（双精度）功能

```java
// Java Program to show the functions
// of dimension class(Double precision)
import java.awt.*;

class dimen {

// Main Method
    public static void main(String args[])
    {

// create dimension
        Dimension d = new Dimension();
        Dimension d1 = new Dimension(20, 30);
        Dimension d2 = new Dimension(d1);

// set height and width of dimension d
        d.setSize(30.3, 30.45);

// equating dimensions
        System.out.println("Dimension d and d1" +
                "are equal = " + d.equals(d1));

        System.out.println("Dimension d and d1" +
                "are equal = " + d1.equals(d2));

// print hashcode
        System.out.println("Hashcode of Dimension d = "
                                + d.hashCode());

// display dimension
        System.out.println("See the values are rounded" +
                        "off to ceiling in dimension d");
        display(d, "Dimension d");
        display(d1, "Dimension d1");
        display(d2, "Dimension d2");
    }

// display dimension
    public static void display(Dimension d, String s)
    {
        System.out.println(s + " Height = " + d.getHeight()
                        + " Width = " + d.getWidth());
    }
}
```

**输出**

```java
Dimension d and d1are equal = false
Dimension d and d1are equal = true
Hashcode of Dimension d = 1984
See the values are roundedoff to ceiling in dimension d
Dimension d Height = 31.0 Width = 31.0
Dimension d1 Height = 30.0 Width = 20.0
Dimension d2 Height = 30.0 Width = 20.0
```

**参考**：[`https://docs.oracle.com/javase/7/docs/api/java/awt/Dimension.html`](https://docs.oracle.com/javase/7/docs/api/java/awt/Dimension.html)