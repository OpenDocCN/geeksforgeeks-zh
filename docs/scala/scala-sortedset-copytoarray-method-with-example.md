# Scala SortedSet copyToArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-copy to array-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-copytoarray-method-with-example/)

**copyToArray()** 方法用于将排序集的元素复制到数组中。

> **方法定义:** def copyToArray(xs: Array[A]，start: Int，len: Int):单位
> 
> **参数:**
> **xs:** 表示复制元素的数组。
> **开始:**表示复制开始的索引。其默认值为 0。
> **len:** 表示要复制的元素数量。它的默认值是排序集的长度。
> 
> **返回类型:**它将 SortedSet 的元素返回到数组中。

**例 1:**

## 斯卡拉

```scala
// Scala program of copyToArray()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedSets
        val s1 = SortedSet(1, 2, 3)

        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

        // Applying copyToArray method
        s1.copyToArray(arr)

        // Displays output
        for(elem <- arr) 
        println(elem)

    }
}
```

**Output:** 

```scala
1
2
3
0
0
```

**例 2:**

## 斯卡拉

```scala
// Scala program of copyToArray()
// method
import scala.collection.immutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedSets
        val s1 = SortedSet(1, 2, 3)

        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

        // Applying copyToArray method
        s1.copyToArray(arr, 1, 2)

        // Displays output
        for(elem <- arr) 
        println(elem)

    }
}
```

**Output:** 

```scala
0
1
2
0
0
```