# Java 数学 copySign()方法，带示例

> 原文: [https://www.geeksforgeeks.org/java-math-copysign-method-examples/](https://www.geeksforgeeks.org/java-math-copysign-method-examples/)

`java.lang.Math.copySign()`方法返回第一个参数和第二个参数的符号。

**注:**
参数可以有两种类型:

- `copySign(double magt, double sign)`
- `copySign(float magt, float sign)`

**语法:**

```java
public static double copySign(DataType magt, DataType sign)
Parameter :
 magt: argument providing the magnitude of the result.
 sign : argument providing the sign of the result.
Return :
This method returns the magnitude of the first argument with the sign of the 
second argument.
```

**示例:** 展示`java.lang.Math.copySign()`方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.copySign() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = 34.543;
        double b = -123.44;

// Input a, b
        // Output -34.543( a- Magnitude, b- Sign)
        System.out.println(Math.copySign(a, b));

// Input b, a
        // Output 123.44( b- Magnitude, a- Sign)
        System.out.println(Math.copySign(b, a));

        float c = 87.56f;
        float d = -685.23f;

// Input c, d
        // Output -87.56( c- Magnitude, d- Sign)
        System.out.println(Math.copySign(c, d));

// Input d, c
        // Output 685.23( d- Magnitude, c- Sign)
        System.out.println(Math.copySign(d, c));
    }
}
```

**输出:**

```java
-34.543
123.44
-87.56
685.23
```