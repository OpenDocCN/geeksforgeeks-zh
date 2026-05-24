# Java 双功能接口方法 – `apply()` 和 `andThen()`

> 原文: [https://www.geeksforgeeks.org/java-bifunction-interface-methods-apply-and-addthen/](https://www.geeksforgeeks.org/java-bifunction-interface-methods-apply-and-addthen/)

`BiFunction` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受两个参数并产生一个结果的函数。

因此，该函数式接口采用 3 个类型参数，即：

*   `T`：表示函数第一个参数的类型
*   `U`：表示函数第二个参数的类型
*   `R`：表示函数的返回类型

分配给 `BiFunction` 类型对象的 Lambda 表达式用于定义其 `apply()` 方法，该方法最终将给定函数应用于参数。使用 `BiFunction` 的主要优点是，它允许我们使用 2 个输入参数，而在 `Function` 中，我们只能有 1 个输入参数。

## `BiFunction` 接口中的方法

`BiFunction` 接口由以下两个主要方法组成：

### 1. `apply()`

此方法将给定的函数应用于参数。

**语法：**

```java
R apply(T t, U u)
```

**参数：** 该方法取两个参数：

*   `t` – 第一个函数参数
*   `u` – 第二个函数参数

**返回：** 该方法返回 `R` 类型的函数结果。

下面是说明 `apply()` 方法的代码：

**程序 1：**

```java
// Java Program to demonstrate
// BiFunction's apply() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction to add 2 numbers
        BiFunction<Integer, Integer, Integer> add = (a, b) -> a + b;

        // Implement add using apply()
        System.out.println("Sum = " + add.apply(2, 3));

        // BiFunction to multiply 2 numbers
        BiFunction<Integer, Integer, Integer> multiply = (a, b) -> a * b;

        // Implement add using apply()
        System.out.println("Product = " + multiply.apply(2, 3));
    }
}
```

**输出：**

```java
Sum = 5
Product = 6
```

### 2. `andThen()`

它返回一个组合函数，其中作为参数传递的函数将在当前 `BiFunction` 之后执行。如果对任一函数的计算引发错误，它将被传递给组合函数的调用方。

**注意：** 作为参数传递的函数应该是 `Function` 类型，而不是 `BiFunction` 类型。

**语法：**

```java
default <V> BiFunction<T, U, V> andThen(Function<? super R, ? extends V> after)
```

其中 `V` 是 `after` 函数和组合函数的输出类型。

**参数：** 该方法接受一个参数 `after`，该参数是此函数之后要应用的函数。

**返回值：** 该方法返回一个组合函数，首先应用当前函数，然后应用 `after` 函数。

**异常：** 如果 `after` 函数为 `null`，该方法抛出 `NullPointerException`。

下面是说明 `andThen()` 方法的代码：

**程序 1：**

```java
// Java Program to demonstrate
// BiFunction's andThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction to demonstrate composite functions
        // Here it will find the sum of two integers
        // and then return twice their sum
        BiFunction<Integer, Integer, Integer> composite1 = (a, b) -> a + b;

        // Using andThen() method
        composite1 = composite1.andThen(a -> 2 * a);

        // Printing the results
        System.out.println("Composite1 = " + composite1.apply(2, 3));

        // BiFunction to demonstrate composite functions
        // Here it will find the sum of two integers
        // and then return twice their sum
        BiFunction<Integer, Integer, Integer> composite2 = (a, b) -> a * b;

        // Using andThen() method
        composite2 = composite2.andThen(a -> 3 * a);

        // Printing the result
        System.out.println("Composite2 = " + composite2.apply(2, 3));
    }
}
```

**输出：**

```java
Composite1 = 10
Composite2 = 18
```

**程序 2：** 演示何时返回 `NullPointerException`。

```java
// Java Program to demonstrate
// BiFunction's andThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction which finds the sum of 2 integers
        // and returns twice their sum
        BiFunction<Integer, Integer, Integer> composite = (a, b) -> a + b;

        try {
            // Using andThen() method
            composite = composite.andThen(null);

            // Printing the result
            System.out.println("Composite = " + composite.apply(2, 3));
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

**程序 3：** 演示 `after` 函数中的异常是如何返回和处理的。

在下面的程序中，当 `(2, 3)` 作为参数传递给第一个函数时，它返回和 `5`。现在这个和将作为参数传递给 `after` 函数，即 `andThen()` 方法。这里，将 `5` 传递给 `after` 函数会产生 `(5 - 5 = 0)`，即分母将变为 `0`。因此将引发算术异常。这个异常将在 `apply()` 函数中处理，而不是 `andThen()` 函数。

```java
// Java Program to demonstrate
// BiFunction's andThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction which finds the sum of 2 integers
        // and returns twice their sum
        BiFunction<Integer, Integer, Integer> composite = (a, b) -> a + b;

        // Using andThen() method
        composite = composite.andThen(a -> a / (a - 5));

        try {
            // Printing the result using apply()
            System.out.println("Composite = " + composite.apply(2, 3));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.ArithmeticException: / by zero
```

**注：**

*   不可能使用 `andThen()` 向现有的 `BiFunction` 添加一个 `BiFunction`。
*   `BiFunction` 接口在需要传递 2 个参数时很有用，不像 `Function` 接口只允许传递一个参数。但是，可以级联两个或多个函数对象来形成 `BiFunction`，但在这种情况下，不可能同时使用这两个参数。这就是 `BiFunction` 的效用。
*   Lambda 表达式被用来初始化 `BiFunction` 接口中的 `apply()` 方法。