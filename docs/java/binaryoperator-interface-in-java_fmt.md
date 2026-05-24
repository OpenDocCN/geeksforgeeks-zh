# Java 中的 BinaryOperator 接口

> 原文：[`https://www.geeksforgeeks.org/binaryoperator-interface-in-java/`](https://www.geeksforgeeks.org/binaryoperator-interface-in-java/)

`BinaryOperator<T>` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个二元运算符，该运算符接受两个操作数并对其进行运算以产生一个结果。然而，它与普通 `BiFunction` 的区别在于它的参数和返回类型都是相同的。

该函数接口采用一个通用类型 `T`，即：
*   `T`：表示操作的输入参数和返回值的类型。

`BinaryOperator<T>` 扩展了 `BiFunction<T, T, T>` 类型。所以它从 `BiFunction` 接口继承了以下方法：
*   `apply(T t, T u)`
*   `andThen(Function<? super R, ? extends V> after)`

分配给 `BinaryOperator` 类型的对象的 lambda 表达式用于定义其 `apply()` 方法，该表达式最终对其参数应用给定的操作。

## BinaryOperator 接口中的方法

`BinaryOperator` 接口由以下方法组成：

### 1. `maxBy()`

此方法返回一个 `BinaryOperator`，它根据给定的比较器返回两个元素中较大的一个。

**语法：**

```java
static <T> BinaryOperator<T> maxBy(Comparator<? super T> comparator)
```

**参数：** 它只接受一个参数，即 `comparator`，它是 `Comparator` 类的一个对象。

**返回值：** 这个方法返回一个 `BinaryOperator`，当基于给定的比较器调用它时，它返回两个对象中的最大值。

下面是演示 `maxBy()` 方法的代码：

**程序：**

```java
import java.util.function.BinaryOperator;

public class GFG {
    public static void main(String args[]) {
        BinaryOperator<Integer> op = BinaryOperator.maxBy(
            (a, b) -> (a > b) ? 1 : ((a == b) ? 0 : -1)
        );

        System.out.println(op.apply(98, 11));
    }
}
```

**输出：**

```java

```