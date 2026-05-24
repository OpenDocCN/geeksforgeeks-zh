# Java 中的 LongFunction 接口

> 原文：[https://www.geeksforgeeks.org/longfunction-interface-in-java-with-examples/](https://www.geeksforgeeks.org/longfunction-interface-in-java-with-examples/)

`LongFunction`接口是从 Java 8 开始引入的`java.util.function`包的一部分，用于在Java中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受`long`值参数并产生类型为`R`的结果的函数。

该功能接口只接受一个泛型，即：

*   `R`：表示此函数的输出类型。

分配给`LongFunction`类型的对象的lambda表达式用于定义其`apply()`方法，该方法最终将给定的操作应用于其唯一的参数。类似于使用`Function<Long, R>`类型的对象。

## 方法

### `apply()`

此方法接受`long`值参数，并给出`R`类型的结果。

**语法：**

```java
R apply(long value)
```

**参数：** 此方法接受一个参数`value`，这是一个`long`值参数。

**返回：** 该方法返回类型为`R`的值。

下面是说明`apply()`方法的代码：

**程序**

```java
import java.util.function.LongFunction;

public class Main {
    public static void main(String args[])
    {
        LongFunction<Double> ob = a -> a / 2.0;

        // Using apply()
        System.out.println(ob.apply(3));
    }
}
```

**输出：**

```java
1.5
```