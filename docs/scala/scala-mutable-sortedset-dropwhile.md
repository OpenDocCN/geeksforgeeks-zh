# Scala 可变排序集 dropWhile()

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-drop while/](https://www.geeksforgeeks.org/scala-mutable-sortedset-dropwhile/)

在 Scala 可变集合中， **dropWhile()** 方法用于从满足所述条件的 SortedSet 中删除最长的元素前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:sorted set[A]
> 
> **返回类型:**从满足规定条件的排序集中删除最长的元素前缀后，返回包含所有元素的树集。

**示例#1:**

```scala
// Scala program of dropWhile() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        var s1 = SortedSet(1, 3, 5, 4, 2) 

        // Print the SortedSet
        println(s1)

        // Applying dropWhile method 
        var res = s1.dropWhile(x => {x % 2 != 0}) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet(2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of dropWhile() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        var s1 = SortedSet(15, 17, 21) 

        // Print the SortedSet
        println(s1)

        // Applying dropWhile method 
        var res = s1.dropWhile(x => {x % 3 == 0}) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
TreeSet(15, 17, 21)
TreeSet(17, 21)

```