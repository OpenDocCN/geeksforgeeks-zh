# Scala Queue init()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-init-method-with-example/](https://www.geeksforgeeks.org/scala-queue-init-method-with-example/)

**init()** 方法用于返回一个新队列，该队列由除最后一个元素之外的所有元素组成。

> **方法定义:**定义初始化:队列[A]
> 
> **返回类型:**它返回一个新的队列，该队列由除最后一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of init() 
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

        // Applying init method 
        val result = q1.init

        // Display output
        print("Elements of the queue except the last one: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Elements of the queue except the last one: Queue(1, 3, 2, 7, 6)

```

**例 2:**

```scala
// Scala program of init() 
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

        // Applying init method 
        val result = q1.init

        // Display output
        print("Elements of the queue except the last one: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 3, 2, 7, 6, 1)
Elements of the queue except the last one: Queue(5, 3, 2, 7, 6)

```