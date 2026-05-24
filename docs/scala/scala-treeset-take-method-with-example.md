# Scala TreeSet take()方法示例

> 原文:[https://www . geesforgeks . org/Scala-treeset-take-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-take-method-with-example/)

**take()** 方法用于返回由树集合的前 n 个元素组成的树集合。

> **方法定义:** def take(n: Int): TreeSet[A]
> 
> **返回类型:**它返回一个由 TreeSet 的前 n 个元素组成的 TreeSet。

**示例#1:**

```scala
// Scala program of take() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying take method  
        val result = t1.take(2)

        // Displays output  
        print("TreeSet containing first two elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet containing first two elements: TreeSet(1, 2)

```

**例 2:**

```scala
// Scala program of take() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying take method  
        val result = t1.take(3)

        // Displays output  
        print("TreeSet containing first three elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet containing first three elements: TreeSet(1, 2, 3)

```