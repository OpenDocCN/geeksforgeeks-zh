# Scala Queue +=()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example-4/](https://www.geeksforgeeks.org/scala-queue-method-with-example-4/)

**+=()** 方法用于在给定队列的后面添加一个元素。

> **方法定义:**def+=(elem:A):queue . this . type
> 
> **返回类型:**它返回给定的队列，在其后面添加一个元素。

**示例#1:**

```scala
// Scala program of +=() 
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

        // Applying +=() method 
        val result = q1.+=("geeks")

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
// Scala program of +=() 
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

        // Applying +=() method 
        val result = q1.+=(5)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)

```