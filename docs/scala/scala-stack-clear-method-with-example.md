# Scala Stack clear()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-clear-method-with-example/](https://www.geeksforgeeks.org/scala-stack-clear-method-with-example/)

在 Scala `Stack class`中， **clear()** 方法被用来删除堆栈中的所有元素。

> **方法定义:** def clear():单位
> 
> **返回类型:**返回空队列。

**示例#1:**

```scala
// Scala program of clear() 
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
        println("Before clear() method: " + s1)  

        // Applying clear method  
        val result = s1.clear  

        // Displays output  
        print("After clear() method: " + result)
    } 
} 
```

**Output:**

```scala
Before clear() method: Stack(1, 2, 3, 4, 5)
After clear() method: ()

```

**例 2:**

```scala
// Scala program of clear() 
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
        val s1 = Stack("geeks", "for", "geeks")  

        // Print the stack 
        println("Before clear() method: " + s1)  

        // Applying clear method  
        val result = s1.clear  

        // Displays output  
        print("After clear() method: " + result)
    } 
} 
```

**Output:**

```scala
Before clear() method: Stack(geeks, for, geeks)
After clear() method: ()

```