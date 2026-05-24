# Scala 可变排序映射 `toSet()` 方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedmap-toset-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-toset-method-with-example/)

## `toSet()` 方法

`toSet()` 方法用于显示 Scala `SortedMap` 中的一个集合。

> **方法定义:** `def toSet: Set[(A, B)]`
>
> **返回类型:** 从指定的排序映射中返回一组。

## 示例

### 示例 #1

```scala
// Scala program of toSet()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 4 -> "for")

// Applying toSet method
        val result = m1.toSet

// Displays output
        println(result)

}
}
```

**输出:**

```scala
Set((3, geeks), (4, for))
```

### 示例 #2

```scala
// Scala program of toSet()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 2 -> "cs")

// Applying toSet method
        val result = m1.toSet

// Displays output
        println(result)

}
}
```

**输出:**

```scala
Set((2, cs), (3, geeks), (4, for))
```