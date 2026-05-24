# Scala 队列 dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-queue-dropwhile-method-with-example/)

**dropWhile()** 方法用于从前面丢弃满足队列中给定谓词的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:Queue[A]
> 
> **返回类型:**在删除满足给定谓词的最长前缀后，它返回一个由元素组成的新队列。

**示例#1:**

```scala
// Scala program of dropWhile() 
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
        val q1 = Queue(2, 4, 6, 1, 8, 3, 5) 

        // Print the queue
        println(q1)

        // Applying dropWhile method 
        val result = q1.dropWhile(x => {x % 2 == 0}) 

        // Displays output 
        print("Queue after using dropWhile() method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(2, 4, 6, 1, 8, 3, 5)
Queue after using dropWhile() method: Queue(1, 8, 3, 5)

```

**例 2:**

```scala
// Scala program of dropWhile() 
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

        // Applying dropWhile method 
        val result = q1.dropWhile(x => {x % 2 != 0}) 

        // Displays output 
        print("Queue after using dropWhile() method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Queue after using dropWhile() method: Queue(2, 7, 6, 5)

```