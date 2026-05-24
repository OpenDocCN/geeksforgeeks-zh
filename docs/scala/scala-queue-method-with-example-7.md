# Scala Queue ++()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-method-with-example-7/](https://www.geeksforgeeks.org/scala-queue-method-with-example-7/)

**++()** 方法用于返回一个新队列，该队列的所有元素都附加在另一个队列的后面。

> **方法定义:**def++【B】>:A】(后缀:IterableOnce【B】):队列【B】
> 
> **返回类型:**它返回一个新队列，该队列的所有元素都附加在另一个队列的后面。

**示例#1:**

```scala
// Scala program of ++() 
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

        // Applying ++() method 
        val result = q1.++(q2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5, 11, 12, 13, 14, 15)

```

**例 2:**

```scala
// Scala program of ++() 
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
        val q1 = Queue("geeks")

        val q2 = Queue("for", "geeks")

        // Applying ++() method 
        val result = q1 ++ q2

        // Display output
        print(result) 

    } 
} 
```

**Output:**

```scala
Queue(geeks, for, geeks)

```