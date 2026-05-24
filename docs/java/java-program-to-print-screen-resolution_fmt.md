# Java 程序打印屏幕分辨率

> 原文：[https://www.geeksforgeeks.org/java-program-to-print-screen-resolution/](https://www.geeksforgeeks.org/java-program-to-print-screen-resolution/)

使用 `Toolkit.getScreenSize()` 方法可以通过一个 Java 程序获得屏幕分辨率。`getScreenSize()` 是 [`java.awt` 包](https://www.geeksforgeeks.org/tag/java-awt/)的 `java.awt.Toolkit` 类的一个方法。它得到了屏幕的大小。在具有多个显示器的系统上，将返回主显示屏分辨率。

1.  `Dimension size = toolkit.getDefaultToolkit().getScreenSize();`
2.  `getScreenSize()` 将以像素为单位返回大小。
3.  如果直接打印尺寸，则显示格式为：`java.awt.Dimension[width=1366, height=768]`

**声明**

```java
public abstract Dimension getScreenSize()
```

**返回：** 当前屏幕的大小，以像素为单位。

**异常**

```java
HeadlessException (if GraphicsEnvironment.isHeadless() returns true)
```

## 代码示例

```java
// Java code to display the screen size
import java.awt.*;

class GFG {
    public static void main(String[] args)
    {
        // getScreenSize() returns the size
        // of the screen in pixels
        Dimension size
            = Toolkit.getDefaultToolkit().getScreenSize();

        // width will store the width of the screen
        int width = (int)size.getWidth();

        // height will store the height of the screen
        int height = (int)size.getHeight();

        System.out.println("Current Screen resolution : "
                           + "width : " + width
                           + " height : " + height);
    }
}
```

**输出：**

![](img/da73a6c29cf73767badee9d7c861cdc7.png)