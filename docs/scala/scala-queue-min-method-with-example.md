# Scala 队列 min()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-min-method-with-example/](https://www.geeksforgeeks.org/scala-queue-min-method-with-example/)

利用 **min()** 方法返回队列的最小元素。

> **方法定义:**定义最小值:A
> 
> **返回类型:**返回队列中最小的元素。

**示例#1:**

```scala
// Scala program of min() 
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

        // Applying min method 
        val result = q1.min

        // Display output
        print("The smallest element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
The smallest element of the queue: 1

```

**例 2:**

```scala
// Scala program of min() 
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
        val q1 = Queue(5, 11, 23, 72, 14, 21, 118) 

        // Print the queue
        println(q1)

        // Applying min method 
        val result = q1.min

        // Display output
        print("The smallest element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 11, 23, 72, 14, 21, 118)
The smallest element of the queue: 5

```