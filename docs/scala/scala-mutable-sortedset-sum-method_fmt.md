# Scala 可变排序集 `sum()` 方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-sum-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-sum-method/)

在 Scala 可变集合中，`sum()` 方法被用来寻找 `SortedSet` 的所有元素的和。

> **方法定义:** `def sum: A`
>
> **返回类型:** 返回 `SortedSet` 中所有元素的总和。

**示例#1:**

```scala
// Scala program of sum()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(40, 10, 2, 3)

        // Applying sum method
        val result = s1.sum

        // Display output
        println(result)
    }
}
```

**Output:**

```scala

```

**例 2:**

```scala
// Scala program of sum()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(2, 6, 5, 8)

        // Applying sum method
        val result = s1.sum

        // Display output
        println(result)
    }
}
```

**Output:**

```scala

```