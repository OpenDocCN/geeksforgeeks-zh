# Scala SortedSet toBuffer() 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-sortedset-tobuffer-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-tobuffer-method-with-example/)

`toBuffer()` 方法用于返回由 `SortedSet` 的所有元素组成的缓冲区。

> **方法定义:** `def toBuffer[B >: A]: Buffer[B]`
>
> **返回类型:** 它返回由 `SortedSet` 的所有元素组成的缓冲区。

## 示例 1

```scala
// Scala program of toBuffer()
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

        // Applying toBuffer method
        val result = s1.toBuffer

        // Display output
        for (elem <- result)
            println(elem)

    }
}
```

**Output:**

```scala

```

## 示例 2

```scala
// Scala program of toBuffer()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(41, 12, 23, 43, 1, 72)

        // Applying toBuffer method
        val result = s1.toBuffer

        // Display output
        for (elem <- result)
            println(elem)

    }
}
```

**Output:**

```scala

```