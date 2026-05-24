# Scala |序列理解

> 原文:[https://www . geesforgeks . org/Scala-sequence-complements/](https://www.geeksforgeeks.org/scala-sequence-comprehensions/)

理解具有(枚举数)*产生 e* 的结构，其中枚举数是指以分号分隔的枚举数列表。[枚举器](https://www.geeksforgeeks.org/enumeration-in-scala/)要么是引入新变量的生成器，要么是过滤器。理解为枚举器生成的每个绑定评估主体 e，并返回这些值的序列。在本文中，Scala 提供了一个轻量级的符号来表达**序列理解**。在测序中，可以在没有平面图的情况下进行多次提取。这可以通过两种方法来实现，一种是使笛卡儿积重复，另一种是对对象列表进行排序。不使用平面图的另一种方法是为 Scala 中的验证计划一种特殊的自动生成语法。
一个**序列理解**语句有一个生成器部分，它从指定的输入范围生成一个值列表，还有一个语句，它对这些生成的元素进行操作，然后存储在输出列表中，在计算结束时返回。支持带过滤器的操作的每个数据类型、[映射](https://www.geeksforgeeks.org/scala-map/)和[平面映射](https://www.geeksforgeeks.org/scala-flatmap-method/)(具有适当的类型)都可以在顺序理解中使用。
我们来了解一些例子。
**示例#1:**

## 斯卡拉

```scala
// Scala program of sequence comprehensions

// Creating an object with extending APP
object CT extends App
{
    // Defining function with sequence comprehensions
    def even(from: Int, to: Int): List[Int] =
    for (a <- List.range(from, to) if a % 4 == 0) yield a
        Console.println(even(0, 20))
}
```

**输出:**

```scala
List(0, 4, 8, 12, 16)
```

在本例中，一个新的整数变量 **i** 被绑定到列表**列表(从，从+ 1，…，到-1)** 的所有值。如果 **i % 4 == 0** 它将从列表中移除所有奇数，并给出 0，20 之间完全可被 4 整除的数字的输出。
**例 2:**

## 斯卡拉

```scala
// Scala program of sequence comprehensions

// Creating object with extending App
object ComprehensionTest2 extends App
{
    // Defining function with sequence comprehensions
    def AddTill(n: Int, x: Int) =
        for (i <- 0 until n;
            j <- i until n if i + j == x) yield
        (i, j);

    // Calling function
    AddTill(12, 20) foreach
    {
        case (i, j) =>
        println(s"($i, $j)")
    }
}
```

**输出:**

```scala
(9, 11)
(10, 10)
```

这里的例子表明序列理解并不局限于列表——每个操作都支持平面图。所以输出会计算 0 到 n-1 之间的所有数对，它们的和等于一个给定值 **x** 。