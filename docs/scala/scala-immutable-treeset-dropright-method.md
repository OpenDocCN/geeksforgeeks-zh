# Scala 不可变 TreeSet dropRight()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-dropright-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-dropright-method/)

在 Scala 不可变的`TreeSet class`中， **dropRight()** 方法被用来删除树集中的最后 n 个元素。

> **方法定义:**def drop right(n:Int):TreeSet[A]
> 
> **返回类型:**它返回一个新的 TreeSet，该 TreeSet 由除最后‘n’个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of dropRight() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying dropRight() method  
        val result = t1.dropRight(2)

        // Displays output 
        println("Queue after using dropRight(2) method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
Queue after using dropRight(2) method: TreeSet(2, 4, 6, 7)

```

**例 2:**

```scala
// Scala program of dropRight() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying dropRight() method  
        val result = t1.dropRight(4)

        // Displays output 
        println("Queue after using dropRight(4) method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
Queue after using dropRight(4) method: TreeSet(2, 4)

```