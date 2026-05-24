# Scala 可变 SortedSet equals()方法

> 原文：[https://www.geeksforgeeks.org/scala-mutable-sortedset-equals-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-equals-method/)

在 Scala 可变集合中，使用 `equals()` 方法检查两个排序集是否有相同的元素。

> **方法定义：** `def equals(that: Any): Boolean`
>
> **返回类型：** 如果两个排序集合的元素相同，则返回 `true`，否则返回 `false`。

**示例 #1：**

```scala
// Scala program of equals()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating SortedSets
        val s1 = SortedSet("geeks", "for", "cs")
        val s2 = SortedSet("cs", "for", "geeks")

        // Applying equals method
        val result = s1.equals(s2)

        // Displays output
        println(result)

    }
}
```

**Output：**

```scala
true
```

**示例 #2：**

```scala
// Scala program of equals()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating SortedSets
        val s1 = SortedSet(11, 10, 2019)
        val s2 = SortedSet(9, 10, 2018)

        // Applying equals method
        val result = s1.equals(s2)

        // Displays output
        println(result)

    }
}
```

**Output：**

```scala
false
```