# Scala Queue toBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-to buffer-method-with-example/](https://www.geeksforgeeks.org/scala-queue-tobuffer-method-with-example/)

**toBuffer()** 方法用于返回由队列的所有元素组成的缓冲区。

> **方法定义:**def to Buffer【B】>:A:Buffer【B】
> 
> **返回类型:**它返回一个包含队列所有元素的缓冲区。

**示例#1:**

```scala
// Scala program of toBuffer() 
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
        val q1 = Queue(1, 2, 3, 4, 5) 

        // Print the queue
        println(q1)

        // Applying toBuffer method 
        val result = q1.toBuffer

        // Display output
        print("Elements in the buffer: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Elements in the buffer: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toBuffer() 
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

        // Applying toBuffer method 
        val result = q1.toBuffer

        // Display output
        print("Elements in the buffer: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Elements in the buffer: 5 2 13 7 1

```