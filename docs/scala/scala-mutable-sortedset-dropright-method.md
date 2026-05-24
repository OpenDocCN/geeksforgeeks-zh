# Scala 可变 SortedSet dropRight()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-drop right-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-dropright-method/)

在 scala 可变集合中， **dropRight()** 用于返回除最后‘n’个元素之外的所有元素。

> **方法定义:**def drop right(n:Int):sorted set[A]
> 
> **返回类型:**返回一个 SortedSet，包含除最后‘n’个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
// method
import scala.collection.mutable.SortedSet 

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
import scala.collection.mutable.SortedSet 

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