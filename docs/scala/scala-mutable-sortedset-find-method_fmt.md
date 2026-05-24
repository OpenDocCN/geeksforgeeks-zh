# Scala 可变排序集 `find()` 方法

> 原文：`https://www.geeksforgeeks.org/scala-mutable-sortedset-find-method/`

在 Scala 可变集合中，`SortedSet` 的 `find()` 方法用于查找 `SortedSet` 中满足给定谓词（如果存在）的第一个元素。

## 方法定义与返回类型

> **方法定义：** `def find(p: (A) => Boolean): Option[A]`
>
> **返回类型：** 返回满足给定谓词的 `SortedSet` 的第一个元素。

## 示例 #1

```scala
// Scala program of find()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a SortedSet
        val s1 = SortedSet(115, 112, 3, 113)

        // Applying find method
        val result = s1.find(_ == 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Some(3)
```

## 示例 #2

```scala
// Scala program of find()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a SortedSet
        val s1 = SortedSet(25, 22, 33, 13)

        // Applying find method
        val result = s1.find(_ == 10)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
None
```