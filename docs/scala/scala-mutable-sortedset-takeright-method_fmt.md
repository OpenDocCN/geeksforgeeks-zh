# Scala 可变排序集 `takeRight()` 方法

> 原文：`https://www.geeksforgeeks.org/scala-mutable-sortedset-takeright-method/`

在 Scala 可变集合中，`takeRight()` 方法用于返回由 `SortedSet` 的最后 n 个元素组成的 `SortedSet`。

> **方法定义：** `def takeRight(n: Int): SortedSet[A]`
> 其中 `n` 指定要选择的元素数量。
>
> **返回类型：** 它返回一个由 `SortedSet` 的最后 n 个元素组成的 `SortedSet`。

## 示例 #1

```scala
// Scala program of takeRight() 
// method 
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{

// Main method 
    def main(args: Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 1)

// Applying takeRight method 
        val result = s1.takeRight(4)

// Display output
        println(result)
    } 
} 
```

**输出：**

```scala
TreeSet(1, 2, 3, 4)
```

## 示例 #2

```scala
// Scala program of takeRight() 
// method 
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{

// Main method 
    def main(args: Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43)

// Applying takeRight method 
        val result = s1.takeRight(3)

// Display output
        println(result)
    } 
} 
```

**输出：**

```scala
TreeSet(23, 41, 43)
```