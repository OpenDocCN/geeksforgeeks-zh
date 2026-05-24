# Scala Queue +:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example-5/](https://www.geeksforgeeks.org/scala-queue-method-with-example-5/)

使用 **+:()** 方法返回一个新的队列，在给定队列的前面添加一个元素。

> **方法定义:**def+:【B】T2:A】(elem:B):队列【B】
> 
> **返回类型:**它返回一个新队列，在给定队列的前面添加了一个元素。

**示例#1:**

```scala
// Scala program of +:() 
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
        val q1 = Queue("for", "geeks") 

        // Applying +:() method 
        val result = q1.+:("geeks")

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)

```

**例 2:**

```scala
// Scala program of +:() 
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
        val q1 = Queue(2, 3, 4, 5, 6) 

        // Applying +:() method 
        val result = q1.+:(1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5, 6)

```