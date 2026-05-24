# Scala Queue equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-equals-method-with-example/](https://www.geeksforgeeks.org/scala-queue-equals-method-with-example/)

**等于()**方法用于检查两个队列是否由相同顺序的相同元素组成。

> **方法定义:** def 等于(o: Any):布尔值
> 
> **返回类型:**如果两个队列相同，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of equals() 
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

        val q2 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println("Queue_1: " + q1)

        println("Queue_2: " + q2)

        // Applying equals method 
        val result = q1.equals(q2) 

        // Displays output 
        print("Queue_1 = Queue_2: " + result)
    } 
} 
```

**Output:**

```scala
Queue_1: Queue(1, 3, 2, 7, 6, 5)
Queue_2: Queue(1, 3, 2, 7, 6, 5)
Queue_1 = Queue_2: true

```

**例 2:**

```scala
// Scala program of equals() 
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

        val q2 = Queue(5, 3, 2, 7, 6, 1) 

        // Print the queue
        println("Queue_1: " + q1)

        println("Queue_2: " + q2)

        // Applying equals method 
        val result = q1.equals(q2) 

        // Displays output 
        print("Queue_1 = Queue_2: " + result)
    } 
} 
```

**Output:**

```scala
Queue_1: Queue(1, 3, 2, 7, 6, 5)
Queue_2: Queue(5, 3, 2, 7, 6, 1)
Queue_1 = Queue_2: false

```