# Scala 队列 splitAt()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-splitat-method-with-example/](https://www.geeksforgeeks.org/scala-queue-splitat-method-with-example/)

splitAt()方法用于在指定的位置将给定的队列拆分成一对前缀/后缀队列。

> **方法定义:** def splitAt(n: Int): (Queue[A]，Queue[A])
> 其中，n 是我们需要拆分的位置。
> 
> **返回类型:**它返回一对由这个队列的前 n 个元素和其他元素组成的队列。

**示例#1:**

```scala
// Scala program of splitAt() 
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

        // Applying splitAt method 
        val result = q1.splitAt(3)

        // Display output
        print(result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
(Queue(5, 2, 13), Queue(7, 1))

```

**例 2:**

```scala
// Scala program of splitAt() 
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

        // Applying splitAt method 
        val result = q1.splitAt(2)

        // Display output
        print(result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
(Queue(5, 2), Queue(13, 7, 1))

```