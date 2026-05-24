# Scala Queue max()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-max-method-with-example/](https://www.geeksforgeeks.org/scala-queue-max-method-with-example/)

利用 **max()** 方法返回队列中最大的方法。

> **方法定义:** def 最大值:A
> 
> **返回类型:**返回队列中最大的元素。

**示例#1:**

```scala
// Scala program of max() 
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

        // Applying max method 
        val result = q1.max

        // Display output
        print("The largest element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
The largest element of the queue: 7

```

**例 2:**

```scala
// Scala program of max() 
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

        // Applying max method 
        val result = q1.max

        // Display output
        print("The largest element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 11, 23, 72, 14, 21, 118)
The largest element of the queue: 118

```