# Scala SortedSet find()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-find-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-find-method-with-example/)

**find()** 方法用于查找满足给定谓词(如果存在)的 SortedSet 的第一个元素。

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**返回满足给定谓词的 SortedSet 的第一个元素。

**示例#1:**

```scala
// Scala program of find() 
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

        // Applying find method 
        val result = s1.find(_ == 3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Some(3)

```

**例 2:**

```scala
// Scala program of find() 
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

        // Applying find method 
        val result = s1.find(_ == 10) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
None

```