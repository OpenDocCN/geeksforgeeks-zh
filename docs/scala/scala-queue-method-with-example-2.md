# Scala Queue ++=()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example-2/](https://www.geeksforgeeks.org/scala-queue-method-with-example-2/)

利用 **++=()** 方法在另一个队列的后面添加一个队列的元素。

> **方法定义:**def++ =(xs:IterableOnce[A]):queue . this . type
> 
> **返回类型:**返回给定的队列，在其末尾添加另一个队列的元素。

**示例#1:**

```scala
// Scala program of ++=() 
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
        val q1 = Queue(3, 4, 5) 

        val q2 = Queue(1, 2) 

        // Applying ++=() method 
        q2.++=(q1) 

        // Display output
        print(q2)   

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of ++=() 
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

        val q2 = Queue("geeks") 

        // Applying ++=() method 
        q2.++=(q1) 

        // Display output
        print(q2)   

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)

```