# Scala Queue toArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-to array-method-with-example/](https://www.geeksforgeeks.org/scala-queue-toarray-method-with-example/)

**toArray()** 用于返回一个由队列所有元素组成的数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**返回一个由队列所有元素组成的数组。

**示例#1:**

```scala
// Scala program of toArray() 
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
        val q1 = Queue(5, 2, 13, 7, 1) 

        // Print the queue
        println(q1)

        // Applying toArray method 
        val result = q1.toArray

        // Display output
        print("Elements in the array: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Elements in the array: 5 2 13 7 1

```

**例 2:**

```scala
// Scala program of toArray() 
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
        val q1 = Queue(15, 2, 13, 7) 

        // Print the queue
        println(q1)

        // Applying toArray method 
        val result = q1.toArray

        // Display output
        print("Elements in the array: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(15, 2, 13, 7)
Elements in the array: 15 2 13 7

```