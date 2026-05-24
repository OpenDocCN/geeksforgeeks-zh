# Scala SortedSet filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-filter-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-filter-method-with-example/)

**过滤器()**方法用于选择满足所述谓词的排序集合的所有元素。

> **方法定义:** def 过滤器(p: (A) = >布尔型:SortedSet[A]
> 
> **返回类型:**它返回一个包含满足给定谓词的 SortedSet 的所有元素的树集。

**示例#1:**

```scala
// Scala program of filter() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a SortedSet 
        val s1 = SortedSet(5, 12, 3, 13) 

        // Applying filter method 
        val result = s1.filter(_ < 10) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
TreeSet(3, 5)

```

**例 2:**

```scala
// Scala program of filter() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a SortedSet 
        val s1 = SortedSet(5, 12, 3, 13) 

        // Applying filter method 
        val result = s1.filter(_ < 3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
TreeSet()

```