# Scala 可变 SortedSet `contains()`方法

> 原文：[`https://www.geeksforgeeks.org/scala-mutable-sortedset-contains-method/`](https://www.geeksforgeeks.org/scala-mutable-sortedset-contains-method/)

在 Scala 中，可变集合 `contains()`方法用于检查一个元素是否存在于 `SortedSet` 中。

## 方法定义

`def contains(elem: A): Boolean`

## 返回类型

如果该元素出现在 `SortedSet` 中，则返回 `true`，否则返回 `false`。

### 示例 1

```scala
// Scala program of contains()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(41, 12, 23, 43, 1, 72)

        // Applying contains() method
        val result = s1.contains(1)

        // Display output
        print(result)
    }
}
```

**Output:**

```scala
true
```

### 示例 2

```scala
// Scala program of contains()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(41, 12, 23, 43, 1, 72)

        // Applying contains() method
        val result = s1.contains(10)

        // Display output
        print(result)
    }
}
```

**Output:**

```scala
false
```