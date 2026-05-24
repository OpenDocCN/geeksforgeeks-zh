# Scala 队列克隆()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-clone-method-with-example/](https://www.geeksforgeeks.org/scala-queue-clone-method-with-example/)

**克隆()**方法用于创建给定队列的副本。

> **方法定义:** defclone():队列[A]
> 
> **返回类型:**它返回一个新队列，该队列是给定队列的副本。

**示例#1:**

```scala
// Scala program of clone() 
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
        val q1 = Queue(10, 11, 12, 13, 14)

        // Print the queue
        println(q1)

        // Applying clone() method 
        val q2 = q1.clone()

        // Display output
        print("Clone of the queue: " + q2)   

    } 
} 
```

**Output:**

```scala
Queue(10, 11, 12, 13, 14)
Clone of the queue: Queue(10, 11, 12, 13, 14)

```

**例 2:**

```scala
// Scala program of clone() 
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
        val q1 = Queue("geeks", "for", "geeks")

        // Print the queue
        println(q1)

        // Applying clone() method 
        val q2 = q1.clone()

        // Display output
        print("Clone of the queue: " + q2)   

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)
Clone of the queue: Queue(geeks, for, geeks)

```