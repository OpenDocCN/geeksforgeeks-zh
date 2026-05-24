# Scala 可变排序集 `exists()` 方法

> 原文：[https://www.geeksforgeeks.org/scala-mutable-sortedset-exists-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-exists-method/)

在 Scala 可变集合中，`SortedSet` 的 `exists()` 方法用于测试谓词是否适用于 `SortedSet` 的某些元素。

> **方法定义：** `def exists(p: (A) => Boolean): Boolean`
>
> **返回类型：** 如果所述谓词对 `SortedSet` 的某些元素成立，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of exists()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val s1 = SortedSet(17, 7, 27, 37)

        // Applying exists method
        val result = s1.exists(y => {y % 3 == 0})

        // Displays output
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
// Scala program of exists()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val s1 = SortedSet(15, 2, 3, 45, 6)

        // Applying exists method
        val result = s1.exists(y => {y % 7 == 0})

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
false
```