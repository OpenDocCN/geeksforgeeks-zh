# Scala Queue dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-queue-dropright-method-with-example/)

**dropRight()** 方法用于丢弃队列的最后 n 个元素。

> **方法定义:** def dropRight(n: Int):队列[A]
> 
> **返回类型:**它返回一个新的队列，该队列由除最后‘n’个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of dropRight() 
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
        val q1 = Queue(1, 2, 3, 4, 5) 

        // Print the queue
        println(q1)

        // Applying dropRight method 
        val result = q1.dropRight(2) 

        // Displays output 
        print("Queue after dropRight(2) method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Queue after dropRight(2) method: Queue(1, 2, 3)

```

**例 2:**

```scala
// Scala program of dropRight() 
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
        val q1 = Queue(1, 2, 3, 4, 5) 

        // Print the queue
        println(q1)

        // Applying dropRight method 
        val result = q1.dropRight(3) 

        // Displays output 
        print("Queue after dropRight(3) method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Queue after dropRight(3) method: Queue(1, 2)

```