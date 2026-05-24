# 带示例的 Java IntFunction 接口

> 原文：[https://www.geeksforgeeks.org/intfunction-interface-in-java-with-examples/](https://www.geeksforgeeks.org/intfunction-interface-in-java-with-examples/)

`IntFunction` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个函数，该函数接受一个整型参数并产生一个类型为 `R` 的结果。

该功能界面只接受一个泛型，即：

*   `R`：表示此函数的输出类型。

分配给 `IntFunction` 类型对象的 lambda 表达式用于定义其 `apply()`，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为 `Function<Integer, R>` 的对象。

`IntFunction` 接口只有一个功能：

### `apply()`

此方法接受一个整型参数，并给出一个 `R` 类型的结果。

**语法：**

```java
R apply(int value)
```

**参数：** 该方法接受一个参数 `value`，这是一个整型参数。

**返回：** 该方法返回类型为 `R` 的值。

下面是说明 `apply()` 方法的代码：

**程序**

```java
import java.util.function.IntFunction;

public class Main {
    public static void main(String args[])
    {
        IntFunction<Double> ob = a -> a / 2.0;

        // Using apply() method
        System.out.println(ob.apply(3));
    }
}
```

**输出：**

```java
1.5
```