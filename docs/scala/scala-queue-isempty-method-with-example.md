# Scala Queue isEmpty()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-queue-isempty-method-with-example/)

**isEmpty()** 用于检查队列是否为空。

> **方法定义:**定义为空:布尔值
> 
> **返回类型:**如果队列为空则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of isEmpty() 
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

        // Applying isEmpty method 
        val result = q1.isEmpty

        // Display output
        print("The queue is empty: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
The queue is empty: false

```

**例 2:**

```scala
// Scala program of isEmpty() 
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
        val q1 = Queue() 

        // Print the queue
        println(q1)

        // Applying isEmpty method 
        val result = q1.isEmpty

        // Display output
        print("The queue is empty: " + result)

    } 
} 
```

**Output:**

```scala
Queue()
The queue is empty: true

```