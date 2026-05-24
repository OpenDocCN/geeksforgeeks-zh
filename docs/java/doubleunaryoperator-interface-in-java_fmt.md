# Java 中的双元运算符接口

> 原文：[https://www.geeksforgeks.org/doubleunaryoperator-interface-in-java/](https://www.geeksforgeks.org/doubleunaryoperator-interface-in-java/)

`DoubleUnaryOperator`接口是从 Java 8 开始引入的`java.util.function`包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示接受一个`double`参数并对其进行运算的函数。它的参数和返回类型都是`double`数据类型。这与使用类型为`UnaryOperator<Double>`的对象非常相似。

分配给`DoubleUnaryOperator`类型的对象的 Lambda 表达式用于定义其`applyAsDouble()`方法，该方法最终会对其参数应用给定的操作。

## `DoubleUnaryOperator`接口中的函数

`DoubleUnaryOperator`接口由以下函数组成：

### 1. `identity()`

这个方法返回一个`DoubleUnaryOperator`，它接受一个`double`值并返回该值。返回的运算符不对其唯一值执行任何操作。

**语法：**

```java
static DoubleUnaryOperator identity()
```

**参数：** 该方法不接受任何参数。

**返回：** 返回一个取一个值并原样返回的`DoubleUnaryOperator`。

下面是说明`identity()`方法的代码：

**程序**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator op = DoubleUnaryOperator.identity();

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**输出：**

```java
12.0
```

### 2. `applyAsDouble()`

此方法接受一个`double`值，执行给定的操作并返回一个`double`值结果。

**语法：**

```java
double applyAsDouble(double operand)
```

**参数：** 该方法采用一个`double`值参数。

**返回：** 返回一个`double`值结果。

下面是演示`applyAsDouble()`方法的代码：

**程序**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator op = a -> 2 * a;

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**输出：**

```java
24.0
```

### 3. `andThen()`

它返回一个复合的`DoubleUnaryOperator`，其中参数化运算符将在当前运算符之后执行。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法：**

```java
default DoubleUnaryOperator andThen(DoubleUnaryOperator after)
```

**参数：** 该方法接受`after`参数，该参数是当前操作之后要应用的操作。

**返回值：** 该方法返回一个由当前操作和`after`操作组成的`DoubleUnaryOperator`，该运算符先应用当前操作，然后应用`after`操作。

**异常：** 如果`after`操作为`null`，该方法抛出`NullPointerException`。

下面是说明`andThen()`方法的代码：

**程序 1：**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator op = a -> 2 * a;

        op = op.andThen(a -> 3 * a);

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**输出：**

```java
72.0
```

**程序 2：** 演示何时返回`NullPointerException`。

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        try {
            DoubleUnaryOperator op = a -> 2 * a;

            op = op.andThen(null);

            System.out.println(op.applyAsDouble(12.0));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.NullPointerException
```

### 4. `compose()`

它返回一个复合的`DoubleUnaryOperator`，其中参数化操作将首先执行，然后是当前操作。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法：**

```java
default DoubleUnaryOperator compose(DoubleUnaryOperator before)
```

**参数：** 该方法接受`before`参数，该参数是先应用的操作，然后是当前操作。

**返回值：** 这个方法返回一个复合的`DoubleUnaryOperator`，在参数化运算符之后应用当前运算符。

**异常：** 如果`before`操作为`null`，该方法抛出`NullPointerException`。

下面是说明`compose()`方法的代码：

**程序 1：**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator op = a -> a / 3;

        op = op.compose(a -> a * 6);

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**输出：**

```java
24.0
```

**程序 2：** 演示何时返回`NullPointerException`。

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        try {
            DoubleUnaryOperator op = a -> a / 3;

            op = op.compose(null);

            System.out.println(op.applyAsDouble(12.0));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.NullPointerException
```