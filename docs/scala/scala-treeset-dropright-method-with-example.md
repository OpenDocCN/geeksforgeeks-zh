# Scala TreeSet dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-dropright-method-with-example/)

在 Scala `TreeSet class`中， **dropRight()** 方法用于删除树集中的最后 n 个元素。

> **方法定义:**def drop right(n:Int):TreeSet[A]
> 
> **返回类型:**它返回一个新的 TreeSet，该 TreeSet 由除最后‘n’个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of dropRight() 
// method 

// Import TreeSet
import scala.collection.mutable._

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
import scala.collection.mutable._

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