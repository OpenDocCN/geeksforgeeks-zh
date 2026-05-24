# Scala Queue count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-count-method-with-example/](https://www.geeksforgeeks.org/scala-queue-count-method-with-example/)

count()方法用于计算队列中满足给定谓词的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**它返回队列中满足给定谓词的元素数量的计数。

**示例#1:**

```scala
// Scala program of count() 
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

        // Print the queue
        println(q1)

        // Applying count method 
        val result = q1.count(z => true) 

        // Displays output 
        print("Number of element in queue: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Number of element in queue: 5

```

**例 2:**

```scala
// Scala program of count() 
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

        // Print the queue
        println(q1)

        // Applying count method 
        val result = q1.count(z => {z % 2 == 0}) 

        // Displays output 
        print("Number of element in queue divisible by 2: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Number of element in queue divisible by 2: 2

```