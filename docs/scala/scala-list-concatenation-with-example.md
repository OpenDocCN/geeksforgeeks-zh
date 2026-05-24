# Scala 列表串联示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-concation-with-example/](https://www.geeksforgeeks.org/scala-list-concatenation-with-example/)

为了连接两个列表，我们需要在 Scala 中使用 **concat()** 方法。
**语法:**

```scala
List.concat(l1, l2)
```

在上面的语法中，l1 是 list1，l2 是 list2。
下面是在 scala 中连接两个列表的例子。
**例 1:**

```scala
// Scala program of concat()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating two lists
        val m1 = List(1, 2, 3)
        val m2 = List(4, 5, 6)

        // Applying concat method
        val res = List.concat(m1, m2)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 2, 3, 4, 5, 6)

```

**例 2:**

```scala
// Scala program of concat()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating two lists
        val m1 = List(1, 2, 3)
        val m2 = List(3, 4, 5)

        // Applying concat method
        val res = List.concat(m1, m2)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 2, 3, 3, 4, 5)

```

这里，相同的元素不会被移除。