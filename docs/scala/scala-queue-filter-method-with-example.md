# Scala Queue 过滤器()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-filter-method-with-example/](https://www.geeksforgeeks.org/scala-queue-filter-method-with-example/)

**filter()** 方法用于返回一个新的队列，该队列由满足给定谓词的所有元素组成。

> **方法定义:** def 过滤器(pred: (A) = >布尔型:队列[A]
> 
> **返回类型:**它返回一个新的队列，该队列由满足给定谓词的所有元素组成。

**示例#1:**

```scala
// Scala program of filter() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying filter method 
        val result = q1.filter(x => {x % 2 == 1}) 

        // Displays output 
        print("Odd elements: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Odd elements: Queue(1, 3, 7, 5)

```

**例 2:**

```scala
// Scala program of filter() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying filter method 
        val result = q1.filter(x => {x % 3 == 0}) 

        // Displays output 
        print("Elements divisible by 3: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Elements divisible by 3: Queue(3, 6)

```