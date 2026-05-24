# Scala Queue clear()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-clear-method-with-example/](https://www.geeksforgeeks.org/scala-queue-clear-method-with-example/)

clear()方法用于删除队列中的所有元素。

> **方法定义:** def clear():单位
> 
> **返回类型:**返回空队列。

**示例#1:**

```scala
// Scala program of clear() 
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
        println("Before clear() method: " + q1)

        // Applying clear() method 
        q1.clear()

        // Display output
        print("After clear() method: " + q1)   

    } 
} 
```

**Output:**

```scala
Before clear() method: Queue(10, 11, 12, 13, 14)
After clear() method: Queue()

```

**例 2:**

```scala
// Scala program of clear() 
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
        println("Before clear() method: " + q1)

        // Applying clear() method 
        q1.clear()

        // Display output
        print("After clear() method: " + q1)   

    } 
} 
```

**Output:**

```scala
Before clear() method: Queue(geeks, for, geeks)
After clear() method: Queue()

```