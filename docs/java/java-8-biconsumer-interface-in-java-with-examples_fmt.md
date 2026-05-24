# Java 8 | BiConsumer 接口详解与示例

> 原文：[https://www.geeksforgeeks.org/java-8-biconsumer-interface-in-java-with-examples/](https://www.geeksforgeeks.org/java-8-biconsumer-interface-in-java-with-examples/)

## BiConsumer 接口

`BiConsumer` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受两个参数并产生一个结果的函数。然而，这类函数不返回值。

这个函数式接口包含两个泛型，即：
*   `T`：表示操作的第一个输入参数的类型。
*   `U`：表示操作的第二个输入参数的类型。

分配给 `BiConsumer` 类型对象的 Lambda 表达式用于定义其 `accept()` 方法，该方法最终将给定的操作应用于其参数。

`BiConsumer` 在不需要返回任何值时非常有用，因为它们预期通过副作用进行操作。

## BiConsumer 接口中的功能

`BiConsumer` 接口由以下两个功能组成：

### 1. accept()

此方法接受两个值，并对给定的参数执行操作。

**语法：**

```java
void accept(T t, U u)
```

**参数：** 该方法采用两个参数：
*   `t` – 第一个输入参数。
*   `u` – 第二个输入参数。

**返回：** 该方法不返回值。

下面是说明 `accept()` 方法的代码：

**程序 1：** 使用 `BiConsumer` 的 `accept()` 方法比较两个整数列表的程序。

```java
// Java Program to demonstrate
// BiConsumer's accept() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create the first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create the second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare both lists
        BiConsumer<List<Integer>, List<Integer> >
            equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };
        equals.accept(lista, listb);
    }
}
```

**输出：**

```java
False
```

### 2. andThen()

它返回一个复合 `BiConsumer`，其中参数化的 `BiConsumer` 将在第一个 `BiConsumer` 之后执行。如果任一操作的计算引发错误，它将被中继到复合操作的调用方。

**注意：** 作为参数传递的操作应为 `BiConsumer` 类型。

**语法：**

```java
default BiConsumer<T, U> andThen(BiConsumer<? super T, ? super U> after)
```

**参数：** 该方法接受 `after` 参数，该参数是当前操作之后要应用的 `BiConsumer`。
**返回值：** 该方法返回一个复合 `BiConsumer`，首先应用当前操作，然后应用 `after` 操作。
**异常：** 如果 `after` 操作为 `null`，该方法抛出 `NullPointerException`。

下面是说明 `andThen()` 方法的代码：

**程序 1：**

```java
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        // Using andThen() method
        equals.andThen(disp).accept(lista, listb);
    }
}
```

**输出：**

```java
False
2 1 3 
2 1 2
```

**程序 2：** 演示 `NullPointerException` 何时被抛出。

```java
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        try {
            equals.andThen(null).accept(lista, listb);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出：**

```java
Exception : java.lang.NullPointerException
```

**程序 3：** 演示函数返回后异常是如何处理的。

```java
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            for (int i = 0; i < list1.size(); i++)
                if (list1.get(i) != list2.get(i)) {
                    System.out.println("False");
                    return;
                }
            System.out.println("True");
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        try {
            disp.andThen(equals).accept(lista, listb);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出：**

```java
2 1 3 
2 1 
Exception : java.lang.IndexOutOfBoundsException: Index 2 out of bounds for length 2
```