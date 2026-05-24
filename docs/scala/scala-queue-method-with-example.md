# Scala Queue :+()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example/](https://www.geeksforgeeks.org/scala-queue-method-with-example/)

**:+()** 方法用于返回一个新的队列，在给定队列的后面添加一个元素。

> **方法定义:**def:+【B】T2:A】(elem:B):队列【B】
> 
> **返回类型:**它返回一个新的队列，在给定队列的后面添加一个元素。

**示例#1:**

```scala
// Scala program of :+() 
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

        // Applying :+() method 
        val res = q1.:+(10)

        // Display output
        print(res)   

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5, 10)

```

**例 2:**

```scala
// Scala program of :+() 
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
        val q1 = Queue("geeks", "for")

        // Applying :+() method 
        val res = q1.:+("geeks")

        // Display output
        print(res)   

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)

```