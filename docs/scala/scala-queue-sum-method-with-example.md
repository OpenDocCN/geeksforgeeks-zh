# Scala Queue sum()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-sum-method-with-example/](https://www.geeksforgeeks.org/scala-queue-sum-method-with-example/)

**sum()** 方法用于返回队列中所有元素的总和。

> **方法定义:**定义和:A
> 
> **返回类型:**返回队列所有元素的总和。

**示例#1:**

```scala
// Scala program of sum() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a queue 
        val q1 = Queue(1, 2, 3, 4, 5) 

        // Print the queue
        println(q1)

        // Applying sum method 
        val result = q1.sum

        // Display output
        print("Sum of all elements of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Sum of all elements of the queue: 15

```

**例 2:**

```scala
// Scala program of sum() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a queue 
        val q1 = Queue(5, 2, 13, 7, 1) 

        // Print the queue
        println(q1)

        // Applying sum method 
        val result = q1.sum

        // Display output
        print("Sum of all elements of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Sum of all elements of the queue: 28

```