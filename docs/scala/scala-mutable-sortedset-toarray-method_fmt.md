# Scala 可变排序集 `toArray()` 方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-toarray-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-toarray-method/)

在 Scala 可变集合中，`toArray()` 用于返回由 `SortedSet` 的所有元素组成的数组。

> **方法定义:** `def toArray: Array[A]`
>
> **返回类型:** 它返回一个由 `SortedSet` 的所有元素组成的数组。

## 示例 #1:

```scala
// Scala program of toArray()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(22, 3, 44, 77)

        // Applying toArray method
        val result = s1.toArray

        // Display output
        for (elem <- result)
            println(elem)
    }
}
```

**Output:**

```scala

```

## 例 2:

```scala
// Scala program of toArray()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(443, 451, 772)

        // Applying toArray method
        val result = s1.toArray

        // Display output
        for (elem <- result)
            println(elem)
    }
}
```

**Output:**

```scala

```