# Scala Queue exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-exists-method-with-example/](https://www.geeksforgeeks.org/scala-queue-exists-method-with-example/)

**exists()** 方法用于检查谓词是否适用于队列的任何元素。

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果谓词对队列的任何元素都成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists() 
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

        // Applying exists method 
        val result = q1.exists(x => {x % 7 == 0}) 

        // Displays output 
        print("Element divisible by 7 exists: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Element divisible by 7 exists: true

```

**例 2:**

```scala
// Scala program of exists() 
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

        // Applying exists method 
        val result = q1.exists(x => {x == 10}) 

        // Displays output 
        print("Element 10 exists: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Element 10 exists: false

```