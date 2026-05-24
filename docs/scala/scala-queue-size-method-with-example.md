# Scala 队列大小()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-size-method-with-example/](https://www.geeksforgeeks.org/scala-queue-size-method-with-example/)

**size()** 方法用于返回队列中存在的元素数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回队列中存在的元素数量。

**示例#1:**

```scala
// Scala program of size() 
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
        val q1 = Queue(5, 2, 3, 7, 1) 

        // Print the queue
        println(q1)

        // Applying size method 
        val result = q1.size

        // Display output
        print("Number of elements in the queue: "  + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 3, 7, 1)
Number of elements in the queue: 5

```

**例 2:**

```scala
// Scala program of size() 
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
        val q1 = Queue("a", "e", "i", "o", "u") 

        // Print the queue
        println(q1)

        // Applying size method 
        val result = q1.size

        // Display output
        print("Number of elements in the queue: "  + result)

    } 
} 
```

**Output:**

```scala
Queue(a, e, i, o, u)
Number of elements in the queue: 5

```