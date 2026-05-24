# Java 中的 LongUnaryOperator 接口

> 原文: [https://www.geeksforgeeks.org/longunaryoperator-interface-in-java/](https://www.geeksforgeeks.org/longunaryoperator-interface-in-java/)

`LongUnaryOperator` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示接受一个参数并对其进行运算的函数。它的参数和返回类型都是 `long` 数据类型。这与使用类型为 [`UnaryOperator`](https://www.geeksforgeeks.org/unaryoperator-interface-in-java/) 的对象非常相似。

分配给 `UnaryOperator` 类型的对象的 lambda 表达式用于定义其 `applyAsLong()` 方法，该表达式最终对其参数应用给定的操作。

## LongUnaryOperator 接口中的函数

`LongUnaryOperator` 界面由以下功能组成:

### 1. `identity()`

这个方法返回一个 `LongUnaryOperator`，它接受一个 `long` 值并返回。返回的 `LongUnaryOperator` 不对其唯一值执行任何操作。

**语法:**

```java
static LongUnaryOperator identity()
```

**参数:** 该方法不接受任何参数

**返回:** 取一个值并返回的 `LongUnaryOperator`。

下面是说明 `identity()` 方法的代码:

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        LongUnaryOperator
            op
            = LongUnaryOperator.identity();

        System.out.println(op.applyAsLong(12));
    }
}
```

**Output:**

```java

```

### 2. `applyAsLong()`

这个方法接受一个 `long` 值，执行给定的操作并返回一个 `long` 值结果。

**语法:**

```java
long applyAsLong(long operand)
```

**参数:** 该方法采用一个 `long` 值参数

**返回:** 返回 `long` 值结果。

下面是说明 `applyAsLong()` 方法的代码:

**程序**

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        LongUnaryOperator
            op
            = a -> 2 * a;

        System.out.println(op.applyAsLong(12));
    }
}
```

**Output:**

```java

```

### 3. `andThen()`

它返回一个组合的 `LongUnaryOperator`，其中参数化运算符将在第一个运算符之后执行。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```java
default LongUnaryOperator andThen(LongUnaryOperator after)
```

**参数:** 该方法接受 `after` 参数，该参数是当前操作之后要应用的操作。

**返回值:** 该方法返回一个组合的 `LongUnaryOperator`，先应用当前操作，后应用 `after` 操作。

**异常:** 如果 `after` 操作为空，该方法抛出 `NullPointerException`。

下面是说明 `andThen()` 方法的代码:

**程序 1:**

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        LongUnaryOperator op = a -> 2 * a;

        op = op.andThen(a -> 3 * a);

        System.out.println(op.applyAsLong(12));
    }
}
```

**Output:**

```java

```

**程序 2:** 演示何时返回 `NullPointerException`。

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        try {

            LongUnaryOperator op = a -> 2 * a;

            op = op.andThen(null);

            System.out.println(op.applyAsLong(12));
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException
```

### 4. `compose()`

它返回一个组合的 `LongUnaryOperator`，其中参数化操作将首先执行，然后是第一个操作。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```java
default LongUnaryOperator compose(LongUnaryOperator before)
```

**参数:** 该方法接受 `before` 参数，该参数是先应用的操作，然后是当前操作。

**返回值:** 这个方法返回一个组合的 `LongUnaryOperator`，在参数化运算符之后应用当前运算符。

**异常:** 如果 `before` 操作为空，该方法抛出 `NullPointerException`。

下面是说明 `compose()` 方法的代码:

**程序 1:**

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        LongUnaryOperator op = a -> a / 3;

        op = op.compose(a -> a * 6);

        System.out.println(op.applyAsLong(12));
    }
}
```

**Output:**

```java

```

**程序 2:** 演示何时返回 `NullPointerException`。

```java
import java.util.function.LongUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        try {

            LongUnaryOperator op = a -> a / 3;

            op = op.compose(null);

            System.out.println(op.applyAsLong(12));
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException
```