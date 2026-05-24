# Scala Stack mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-stack-mkstring-method-with-example/)

在 Scala `Stack class`中， **mkString()** 方法用于显示字符串中堆栈的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**返回一个包含栈中所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
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
        val s1 = Stack(1, 2, 3, 4) 

        // Print the stack 
        println(s1) 

        // Applying mkString method  
        val result = s1.mkString

        // Display output 
        print("Stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Stack: 1234

```

**例 2:**

```scala
// Scala program of mkString() 
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
        val s1 = Stack("Geeks", "for", "Geeks") 

        // Print the stack 
        println(s1) 

        // Applying mkString method  
        val result = s1.mkString

        // Display output 
        print("Stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(Geeks, for, Geeks)
Stack: GeeksforGeeks

```