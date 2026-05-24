# Scala Queue ++:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example-6/](https://www.geeksforgeeks.org/scala-queue-method-with-example-6/)

**++:()** 方法用于返回一个新队列，该队列的所有元素都附加在另一个队列的前面。

> **方法定义:**def++:【B】T2:【A】(前缀:IterableOnce【B】):队列【B】
> 
> **返回类型:**它返回一个新队列，该队列的所有元素都附加在另一个队列的前面。

**示例#1:**

```scala
// Scala program of ++:() 
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

        val q2 = Queue(11, 12, 13, 14, 15) 

        // Applying ++:() method 
        val result = q1.++:(q2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(11, 12, 13, 14, 15, 1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of ++:() 
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

        // Applying ++:() method 
        val result = q1.++:(q2) 

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)

```