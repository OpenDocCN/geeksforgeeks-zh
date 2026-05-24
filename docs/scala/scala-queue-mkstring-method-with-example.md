# Scala Queue mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-queue-mkstring-method-with-example/)

**mkString()** 方法用于显示字符串中队列的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**返回一个包含队列所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
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
        val q1 = Queue(1, 2, 3, 4) 

        // Print the queue
        println(q1)

        // Applying mkString method 
        val result = q1.mkString

        // Display output
        print("Queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4)
Queue: 1234

```

**例 2:**

```scala
// Scala program of mkString() 
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
        val q1 = Queue("Geeks", "Will", "Rule") 

        // Print the queue
        println(q1)

        // Applying mkString method 
        val result = q1.mkString

        // Display output
        print("Queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(Geeks, Will, Rule)
Queue: GeeksWillRule

```