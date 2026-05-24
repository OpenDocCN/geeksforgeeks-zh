# Scala 可变排序集& ~()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-method-5/](https://www.geeksforgeeks.org/scala-mutable-sortedset-method-5/)

在 Scala 可变集合 **& ~()** 中，使用方法在两个给定排序集之间的差异之后创建一个由元素组成的新排序集。

> **方法定义:**定义& ~(即:排序集[A]):排序集[A]
> 
> **返回类型:**它返回一个由两个给定排序集之间的差异后的元素组成的树集。

**示例#1:**

```scala
// Scala program of &~() method  
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        val s2 = SortedSet(1, 100, 5, 12, 23)

        // Applying &~() method 
        val result = s1 &~(s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet(41, 43, 72)

```

**例 2:**

```scala
// Scala program of &~() method  
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 5, 3, 4) 

        val s2 = SortedSet(2, 4)

        // Applying &~() method 
        val result = s2 &~(s1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet()

```