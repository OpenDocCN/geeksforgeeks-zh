# 带分隔符的 Scala Queue mkString()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-queue-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-queue-mkstring-method-with-a-separator-with-example/)

**mkString()** 方法用于显示字符串中队列的所有元素以及分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它返回一个字符串中队列的所有元素以及一个分隔符。

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
        val result = q1.mkString(", ")

        // Display output
        print("Queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4)
Queue: 1, 2, 3, 4

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
        val result = q1.mkString(", ")

        // Display output
        print("Queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(Geeks, Will, Rule)
Queue: Geeks, Will, Rule

```