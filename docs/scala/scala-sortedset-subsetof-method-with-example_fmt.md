# Scala sorted set subsetOf()方法示例

> 原文: `https://www.geeksforgeeks.org/scala-sortedset-subsetof-method-with-example/`

`subsetOf()`方法用于测试一个排序集是否是另一个排序集的子排序集。

## 方法定义

def subsetOf(that: SortedSet[A]): Boolean

**返回类型:** 如果一个排序集是另一个排序集的子集，则返回真，否则返回假。

## 示例#1

```scala
// Scala program of subsetOf() method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(4, 12, 2, 31)
        val s2 = SortedSet(4, 12)

        // Applying subsetOf method
        val result = s2.subsetOf(s1)

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
true
```

## 示例#2

```scala
// Scala program of subsetOf()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(4, 12, 2, 31)
        val s2 = SortedSet(4, 12)

        // Applying subsetOf method
        val result = s1.subsetOf(s2)

        // Display output
        println(result)
    }
}
```

**Output:**

```scala
false
```