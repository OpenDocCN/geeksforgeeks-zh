# Scala Queue last()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-last-method-with-example/](https://www.geeksforgeeks.org/scala-queue-last-method-with-example/)

**last()** 方法用于返回队列的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回队列的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
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
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying last method 
        val result = q1.last

        // Display output
        print("The last element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
The last element of the queue: 5

```

**例 2:**

```scala
// Scala program of last() 
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
        val q1 = Queue(5, 3, 2, 7, 6, 1) 

        // Print the queue
        println(q1)

        // Applying last method 
        val result = q1.last

        // Display output
        print("The last element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 3, 2, 7, 6, 1)
The last element of the queue: 1

```