# Scala 可变排序集 `filter()` 方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-filter-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-filter-method/)

在 Scala 可变集合中，`SortedSet` 的 `filter()` 方法用于选择 `SortedSet` 中满足规定谓词的所有元素。

> **方法定义:** `def filter(p: (A) => Boolean): SortedSet[A]`
>
> **返回类型:** 它返回一个包含满足给定谓词的 `SortedSet` 的所有元素的 `TreeSet`。

## 示例 #1

```scala
// Scala program of filter()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a SortedSet
        val s1 = SortedSet(5, 12, 3, 13)

        // Applying filter method
        val result = s1.filter(_ < 10)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
TreeSet(3, 5)
```

## 示例 #2

```scala
// Scala program of filter()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a SortedSet
        val s1 = SortedSet(5, 12, 3, 13)

        // Applying filter method
        val result = s1.filter(_ < 3)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
TreeSet()
```