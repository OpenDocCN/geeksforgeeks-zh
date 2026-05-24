# Scala Stack foreach()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-foreach-method-with-example/](https://www.geeksforgeeks.org/scala-stack-foreach-method-with-example/)

在 Scala `Stack class`中， **foreach()** 方法用于将给定的函数应用于堆栈的所有元素。

> **方法定义:** def foreach[U](f: (A) = > U):单位
> 
> **返回类型:**在对每个元素应用给定函数后，返回堆栈的所有元素。

**示例#1:**

```scala
// Scala program of foreach() 
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
        val s1 = Stack(6, 2, 3, 4, 5)  

        // Applying foreach method to print the stack 
        print("Elements in the stack: ") 
        s1.foreach(x => print(x + " "))
    } 
} 
```

**Output:**

```scala
Elements in the stack: 6 2 3 4 5

```

**例 2:**

```scala
// Scala program of foreach() 
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
        val s1 = Stack(6, 2, 3, 4, 5)  

        // Print the stack
        println(s1)

        // Applying foreach method  
        s1.foreach(x => println(x + " times " + x +" = " + x*x)) 
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
6 times 6 = 36
2 times 2 = 4
3 times 3 = 9
4 times 4 = 16
5 times 5 = 25

```