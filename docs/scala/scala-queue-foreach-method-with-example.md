# Scala Queue foreach()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-foreach-method-with-example/](https://www.geeksforgeeks.org/scala-queue-foreach-method-with-example/)

**foreach()** 方法用于将给定的函数应用于队列的所有元素。

> **方法定义:** def foreach[U](f: (A) = > U):单位
> 
> **返回类型:**将给定的函数应用到队列的每个元素后，返回队列的所有元素。

**示例#1:**

```scala
// Scala program of foreach() 
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

        // Applying foreach method to print the queue
        print("Elements in the queue: ")
        q1.foreach(x => print(x + " ")) 

    } 
} 
```

**Output:**

```scala
Elements in the queue: 1 3 2 7 6 5

```

**例 2:**

```scala
// Scala program of foreach() 
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

        // Applying foreach method 
        q1.foreach(x => println(x + " times " + x +" = " + x*x)) 

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
1 times 1 = 1
3 times 3 = 9
2 times 2 = 4
7 times 7 = 49
6 times 6 = 36
5 times 5 = 25

```