# Scala SortedSet foreach()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-foreach-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-foreach-method-with-example/)

**foreach()** 方法用于将给定函数应用于排序集合的所有元素。

> **方法定义:** def foreach(f: (A) = >单位:单位
> 
> **返回类型:**将给定的函数应用到 SortedSet 的所有元素后，返回它们。

**示例#1:**

```scala
// Scala program of foreach() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(3, 7, 12, 9, 21) 

        // Applying foreach method 
        s1.foreach(x => println(x)) 

    } 
} 
```

**Output:**

```scala
3
7
9
12
21

```

**例 2:**

```scala
// Scala program of foreach() 
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

        // Applying foreach method 
        s1.foreach(x => println(x + " times " + x + " = " + x*x)) 

    } 
} 
```

**Output:**

```scala
1 times 1 = 1
2 times 2 = 4
3 times 3 = 9
4 times 4 = 16
5 times 5 = 25

```