# Java 中的 `DoubleConsumer` 接口，示例

> 原文: [https://www.geeksforgeeks.org/doubleconsumer-interface-in-java-with-examples/](https://www.geeksforgeeks.org/doubleconsumer-interface-in-java-with-examples/)

`DoubleConsumer` 接口是 `java.util.function` 包的一部分，该包是从 Java 8 开始引入的，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受一个 `double` 值参数但不返回值的函数。

分配给 `DoubleConsumer` 类型的对象的 lambda 表达式用于定义其 `accept()` 方法，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为 `Consumer<Double>` 的对象。

`DoubleConsumer` 接口由以下两个功能组成:

## `accept()`

此方法接受一个值，并对其唯一的参数执行操作。

### 语法:

```java
void accept(double value)
```

### 参数:
该方法只接受一个参数:
*   `value` – 输入参数

### 返回:
该方法不返回值。

下面是说明 `accept()` 方法的代码:

```java
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {
        // Create a DoubleConsumer Instance
        DoubleConsumer
            display
            = a -> System.out.println(a * 10);

        // using accept() method
        display.accept(3);
    }
}
```

### 输出:

```java
30.0
```

## `andThen()`

它返回一个复合 `DoubleConsumer`，其中参数化的 `DoubleConsumer` 将在第一个 `DoubleConsumer` 之后执行。如果任一操作的计算引发错误，它将被中继到合成操作的调用方。

**注意:** 作为参数传递的操作应为 `DoubleConsumer` 类型。

### 语法:

```java
default DoubleConsumer andThen(DoubleConsumer after)
```

### 参数:
该方法接受 `after` 参数，该参数是当前操作之后要应用的 `DoubleConsumer`。

### 返回值:
这个方法返回一个复合的 `DoubleConsumer`，首先应用当前操作，然后应用 `after` 操作。

### 异常:
如果 `after` 操作为 `null`，该方法抛出 `NullPointerException`。

下面是说明 `andThen()` 方法的代码:

### 程序 1:

```java
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {
        // Create a DoubleConsumer Instance
        DoubleConsumer display = a -> System.out.println(a * 10);
        DoubleConsumer mul = a -> a /= 2;

        // using andThen() method
        DoubleConsumer composite = mul.andThen(display);
        composite.accept(3);
    }
}
```

### 输出:

```java
1.5
30.0
```

### 程序 2:
演示 `NullPointerException` 何时返回。

```java
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {
        // Create a DoubleConsumer Instance
        DoubleConsumer mul = a -> a /= 10;

        try {
            // using andThen() method
            DoubleConsumer composite = mul.andThen(null);
            composite.accept(3);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

### 输出:

```java
Exception : java.lang.NullPointerException
```

### 程序 3:
演示 `after` 函数中的异常是如何返回和处理的。

```java
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {
        try {
            DoubleConsumer
                conv
                = a
                -> System.out.println(
                    Integer
                        .parseInt(
                            Double
                                .toString(a)));
            DoubleConsumer mul = a -> a /= 10;

            // using andThen() method
            DoubleConsumer composite = mul.andThen(conv);
            composite.accept(3);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

### 输出:

```java
Exception : java.lang.NumberFormatException: For input string: "3.0"
```