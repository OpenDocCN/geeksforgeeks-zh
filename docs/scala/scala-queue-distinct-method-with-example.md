# Scala Queue distinct()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-distinct-method-with-example/](https://www.geeksforgeeks.org/scala-queue-distinct-method-with-example/)

使用 **distinct()** 方法从给定的队列中移除重复的元素。

> **方法定义:**定义不同:队列[A]
> 
> **返回类型:**它返回一个只包含不同元素的新队列。

**示例#1:**

```scala
// Scala program of distinct() 
// method 

// Import Queue 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queue
        val s1 = Queue(2, 1, 3, 2, 1, 2, 3) 

        // Print the queue
        println(s1) 

        // Applying distinct() method  
        val result = s1.distinct

        // Display output 
        print("Queue with distinct elements: " + result) 

    } 
} 
```

**Output:**

```scala
Queue(2, 1, 3, 2, 1, 2, 3)
Queue with distinct elements: Queue(2, 1, 3)

```

**例 2:**

```scala
// Scala program of distinct() 
// method 

// Import Queue 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queue
        val s1 = Queue("g", "e", "e", "k", "s", "f", "o", "r", "g", "e", "e", "k", "s") 

        // Print the queue
        println(s1) 

        // Applying distinct() method  
        val result = s1.distinct

        // Display output 
        print("Queue with distinct elements: " + result) 

    } 
} 
```

**Output:**

```scala
Queue(g, e, e, k, s, f, o, r, g, e, e, k, s)
Queue with distinct elements: Queue(g, e, k, s, f, o, r)

```