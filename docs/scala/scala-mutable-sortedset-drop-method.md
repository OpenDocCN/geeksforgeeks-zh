# Scala 可变 SortedSet drop()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-drop-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-drop-method/)

在 scala 可变集合中， **drop()** 方法用于删除前‘n’个元素或返回除前‘n’个元素之外的所有元素。

> **方法定义:**def drop(n:Int):sorted set[A]]
> 
> **返回类型:**返回除前‘n’个元素外的所有元素。

**示例#1:**

```scala
// Scala program of drop()
// method
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(5, 1, 2, 3, 4)

        // Applying drop method 
        val s2 = s1.drop(2) 

        // Displays output 
        for(elem <- s2) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
3
4
5

```

**例 2:**

```scala
// Scala program of drop()
// method
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(5, 1, 2, 3, 4)

        // Applying drop method 
        val s2 = s1.drop(4) 

        // Displays output 
        for(elem <- s2)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
5

```