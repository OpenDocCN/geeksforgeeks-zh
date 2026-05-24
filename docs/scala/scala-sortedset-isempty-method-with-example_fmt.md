# Scala SortedSet isEmpty()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-sortedset-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-isempty-method-with-example/)

`isEmpty()` 方法用于测试排序集是否为空。

> **方法定义:** `def isEmpty: Boolean`
>
> **返回类型:** `Boolean`。如果 `SortedSet` 为空则返回 `true`，否则返回 `false`。

## 示例 1:

```scala
// Scala program of isEmpty()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(1, 2, 3, 4, 5)

        // Applying isEmpty method
        val result = s1.isEmpty

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
false
```

## 示例 2:

```scala
// Scala program of isEmpty()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet()

        // Applying isEmpty method
        val result = s1.isEmpty

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
true
```