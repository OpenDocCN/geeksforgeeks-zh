# Scala 可变排序集&()方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-method/)

在 Scala 可变集合中，`&()`方法用于创建一个新的排序集，该排序集由给定排序集中的所有元素组成。

> **方法定义:** `def &(that: SortedSet[A]): SortedSet[A]`
>
> **返回类型:** 它返回一个新的排序集，该排序集由给定排序集中的所有元素组成。

## 示例#1

```scala
// Scala program of &() method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(100, 41, 12, 43, 1, 72)
        val s2 = SortedSet(10, 100, 50, 12, 23)

        // Applying &() method
        val result = s1 & (s2)

        // Display output
        print(result)
    }
}
```

**Output:**

```scala
TreeSet(12, 100)
```

## 示例#2

```scala
// Scala program of &() method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(51, 33, 95, 7)
        val s2 = SortedSet(20, 44, 96, 8)

        // Applying &() method
        val result = s1 & (s2)

        // Display output
        print(result)
    }
}
```

**Output:**

```scala
TreeSet()
```