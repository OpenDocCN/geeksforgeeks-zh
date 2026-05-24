# Scala Queue head()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-head-method-with-example/](https://www.geeksforgeeks.org/scala-queue-head-method-with-example/)

利用 **head()** 方法返回队列的第一个元素。

> **方法定义:**定义标题:A
> 
> **返回类型:**返回队列的第一个元素。

**示例#1:**

```scala
// Scala program of head() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying head method 
        val result = q1.head

        // Display output
        print("First element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
First element of the queue: 1

```

**例 2:**

```scala
// Scala program of head() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(5, 3, 2, 7, 6, 1) 

        // Print the queue
        println(q1)

        // Applying head method 
        val result = q1.head

        // Display output
        print("First element of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 3, 2, 7, 6, 1)
First element of the queue: 5

```