# Java toRadians()方法示例

> 原文：[https://www.geeksforgeeks.org/java-toradians-method-example/](https://www.geeksforgeeks.org/java-toradians-method-example/)

`java.lang.Math.toRadians()`用于将以度为单位的角度转换为以弧度为单位的近似等效角度。
**注**：度数到弧度的转换一般不精确。

**语法**：

```java
public static double toRadians(double deg)
```

参数：
`deg`：此参数是我们想要转换为弧度的以度为单位的角度。
返回值：
此方法返回角度`deg`的弧度度量。

**示例**：展示`java.lang.Math.toRadians()`方法的工作。

## 示例代码

```java
// Java program to demonstrate working
// of java.lang.Math.toRadians() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        // converting PI from degree to radian
        double deg = 180.0;
        System.out.println(Math.toRadians(deg));

        // converting PI/2 from degree to radian
        deg = 90.0;
        System.out.println(Math.toRadians(deg));

        // converting PI/4 from degree to radian
        deg = 45.0;
        System.out.println(Math.toRadians(deg));
    }
}
```

**输出**：

```java
3.141592653589793
1.5707963267948966
0.7853981633974483
```