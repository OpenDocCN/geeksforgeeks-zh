# Scala 不可变 TreeSet takeRight()方法

> 原文:[https://www . geeksforgeeks . org/Scala-不可变-treeset-takeright-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-takeright-method/)

在 Scala 不可变树集合类中， **takeRight()** 方法用于返回由树集合的最后 n 个元素组成的树集合。

> **方法定义:**def taker right(n:Int):TreeSet[A]
> 
> **返回类型:**它返回一个由 TreeSet 的最后‘n’个元素组成的 TreeSet。

**示例#1:**

```scala
// Scala program of takeRight() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying takeRight method  
        val result = t1.takeRight(2)

        // Displays output  
        print("TreeSet containing last two elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet containing last two elements: TreeSet(4, 5)

```

**例 2:**

```scala
// Scala program of takeRight() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying takeRight method  
        val result = t1.takeRight(3)

        // Displays output  
        print("TreeSet containing last three elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet containing last three elements: TreeSet(3, 4, 5)

```