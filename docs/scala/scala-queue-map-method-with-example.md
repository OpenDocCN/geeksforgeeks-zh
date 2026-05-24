# Scala Queue map()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-map-method-with-example/](https://www.geeksforgeeks.org/scala-queue-map-method-with-example/)

**map()** 方法用于通过将函数应用于该队列的所有元素来构建新队列。

> **方法定义:** def 图【B】(f:(A)=>B):队列【B】
> 
> **返回类型:**应用给定函数后，返回包含所有元素的新队列。

**示例#1:**

```scala
// Scala program of map() 
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
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying map method 
        val result = q1.map(x => x*x)

        // Display output
        print("New queue after squaring all elements: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
New queue after squaring all elements: Queue(1, 9, 4, 49, 36, 25)

```

**例 2:**

```scala
// Scala program of map() 
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
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying map method 
        val result = q1.map(x => x/2)

        // Display output
        print("New queue after dividing all elements by 2: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
New queue after dividing all elements by 2: Queue(0, 1, 1, 3, 3, 2)

```