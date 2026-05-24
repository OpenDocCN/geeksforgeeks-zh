# Scala 队列查找()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-find-method-with-example/](https://www.geeksforgeeks.org/scala-queue-find-method-with-example/)

**find()** 方法用于返回满足队列中给定谓词的元素。

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**返回满足给定谓词的第一个元素(如果存在)，否则返回无。

**示例#1:**

```scala
// Scala program of find() 
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

        // Applying find method 
        val result = q1.find(x => {x % 7 == 0}) 

        // Displays output 
        print("Element divisible by 7: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Element divisible by 7: Some(7)

```

**例 2:**

```scala
// Scala program of find() 
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

        // Applying find method 
        val result = q1.find(x => {x % 10 == 0}) 

        // Displays output 
        print("Element divisible by 10: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Element divisible by 10: None

```