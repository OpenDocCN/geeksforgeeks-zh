# Scala Queue toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-to list-method-with-example/](https://www.geeksforgeeks.org/scala-queue-tolist-method-with-example/)

**toList()** 方法用于返回一个包含队列所有元素的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个包含队列所有元素的列表。

**示例#1:**

```scala
// Scala program of toList() 
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

        // Applying toList method 
        val result = q1.toList

        // Display output
        print("Elements in the list: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Elements in the list: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toList() 
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

        // Applying toList method 
        val result = q1.toList

        // Display output
        print("Elements in the list: ")

        for(elem <- result)
            print(elem + " ")

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Elements in the list: 5 2 13 7 1

```