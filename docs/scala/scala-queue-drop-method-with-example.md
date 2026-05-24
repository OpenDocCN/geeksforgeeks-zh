# Scala Queue drop()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-drop-method-with-example/](https://www.geeksforgeeks.org/scala-queue-drop-method-with-example/)

**drop()** 方法用于丢弃队列的前 n 个元素。

> **方法定义:** def drop(n: Int):队列[A]
> 
> **返回类型:**它返回一个新的队列，除了前 n 个元素之外，所有元素都在这个队列中。

**示例#1:**

```scala
// Scala program of drop() 
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

        // Applying drop method 
        val result = q1.drop(2) 

        // Displays output 
        print("Queue after drop(2) method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Queue after drop(2) method: Queue(3, 4, 5)

```

**例 2:**

```scala
// Scala program of drop() 
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

        // Applying drop method 
        val result = q1.drop(3) 

        // Displays output 
        print("Queue after drop(3) method: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Queue after drop(3) method: Queue(4, 5)

```