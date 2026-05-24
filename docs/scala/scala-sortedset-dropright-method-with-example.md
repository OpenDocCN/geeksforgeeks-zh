# Scala SortedSet dropRight()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-dropright-method-with-example/)

**dropRight()** 用于返回除最后‘n’个元素之外的所有元素。

> **方法定义:**def drop right(n:Int):sorted set[A]
> 
> **返回类型:**返回一个 SortedSet，包含除最后‘n’个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
// method
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(1, 2, 3, 4, 5)

        // Applying dropRight method 
        val s2 = s1.dropRight(1) 

        // Displays output 
        for(elem <- s2)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
2
3
4

```

**例 2:**

```scala
// Scala program of dropRight()
// method
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(1, 2, 3, 4, 5)

        // Applying dropRight method 
        val s2 = s1.dropRight(2) 

        // Displays output 
        for(elem <- s2)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
2
3

```