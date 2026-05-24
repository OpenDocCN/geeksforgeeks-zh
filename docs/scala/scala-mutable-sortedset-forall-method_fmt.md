# Scala 可变排序集合 `forall()` 方法

> 原文：[https://www.geeksforgeeks.org/scala-mutable-sortedset-forall-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-forall-method/)

在 Scala 可变集合中，`SortedSet` 的 `forall()` 方法用于检查给定的谓词是否满足 `SortedSet` 的所有元素。

**方法定义：**
`def forall(p: (A) => Boolean): Boolean`

**返回类型：**
如果所述谓词对 `SortedSet` 的所有元素都成立，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of forall()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(13, 7, 12, 9, 21)

        // Applying forall method
        val result = s1.forall(y => {y % 3 == 0})

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
false
```

## 示例 2

```scala
// Scala program of forall()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(15, 12, 21, 30)

        // Applying forall method
        val result = s1.forall(y => {y % 3 == 0})

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
true
```