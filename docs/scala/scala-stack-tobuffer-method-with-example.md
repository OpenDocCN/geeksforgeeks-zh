# Scala Stack toBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-to buffer-method-with-example/](https://www.geeksforgeeks.org/scala-stack-tobuffer-method-with-example/)

在 Scala `Stack class`中， **toBuffer()** 方法被用来返回一个包含堆栈所有元素的缓冲区。

> **方法定义:**def to Buffer【B】>:A:Buffer【B】
> 
> **返回类型:**它返回一个由栈的所有元素组成的缓冲区。

**示例#1:**

```scala
// Scala program of toBuffer() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(5, 2, 13, 7, 1) 

        // Print the stack 
        println(s1) 

        // Applying toBuffer method  
        val result = s1.toBuffer

        // Display output 
        print("Elements in the buffer: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
Elements in the buffer: 5 2 13 7 1

```

**例 2:**

```scala
// Scala program of toBuffer() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(1, 2, 3, 4, 5) 

        // Print the stack 
        println(s1) 

        // Applying toBuffer method  
        val result = s1.toBuffer

        // Display output 
        print("Elements in the buffer: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Elements in the buffer: 1 2 3 4 5

```