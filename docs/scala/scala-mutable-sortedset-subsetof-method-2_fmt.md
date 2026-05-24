# Scala 可变 SortedSet subsetOf()方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-subsetof-method-2/](https://www.geeksforgeeks.org/scala-mutable-sortedset-subsetof-method-2/)

在 Scala 可变集合中，`subsetOf()`方法用于测试一个排序集是否是另一个排序集的子排序集。

## 方法定义

`subsetOf(that: SortedSet[A]): Boolean`

## 返回类型

如果一个排序集是另一个排序集的子集，则返回`true`，否则返回`false`。

## 示例 #1

```scala
// Scala program of subsetOf() method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(4, 12, 2, 31)
        val s2 = SortedSet(4, 12)

        // Applying subsetOf method
        val result = s2.subsetOf(s1)

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
true
```

## 示例 #2

```scala
// Scala program of subsetOf() method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(4, 12, 2, 31)
        val s2 = SortedSet(4, 12)

        // Applying subsetOf method
        val result = s1.subsetOf(s2)

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
false
```