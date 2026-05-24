# Scala Queue toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-queue-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-queue-toseq-method-with-example/)

**toSeq()** 方法用于返回由队列的所有元素组成的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**它返回一个包含队列所有元素的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
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

        // Applying toSeq method 
        val result = q1.toSeq

        // Display output
        print("Elements in the Seq: ")

        for (ele <- result) 
            print(ele + " ") 

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Elements in the Seq: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toSeq() 
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
        val q1 = Queue(5, 2, 13, 7, 1, 3) 

        // Print the queue
        println(q1)

        // Applying toSeq method 
        val result = q1.toSeq

        // Display output
        print("Elements in the Seq: ")

        for (ele <- result) 
            print(ele + " ") 

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1, 3)
Elements in the Seq: 5 2 13 7 1 3

```