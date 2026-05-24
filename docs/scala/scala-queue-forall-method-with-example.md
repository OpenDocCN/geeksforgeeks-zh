# Scala Queue forall()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-for all-method-with-example/](https://www.geeksforgeeks.org/scala-queue-forall-method-with-example/)

**forall()** 方法用于检查谓词是否对队列的所有元素都成立。

> **方法定义:**定义为 all(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果谓词对队列的所有元素都成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of forall() 
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

        // Applying forall method 
        val result = q1.forall(x => {x % 7 == 0}) 

        // Displays output 
        print("All the elements are divisible by 7: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
All the elements are divisible by 7: false

```

**例 2:**

```scala
// Scala program of forall() 
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
        val q1 = Queue(1, 3, 7, 5) 

        // Print the queue
        println(q1)

        // Applying forall method 
        val result = q1.forall(x => {x % 2 != 0}) 

        // Displays output 
        print("All the elements are odd: " + result)
    } 
} 
```

**Output:**

```scala
Queue(1, 3, 7, 5)
All the elements are odd: true

```