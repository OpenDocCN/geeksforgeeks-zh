# Scala Stack map()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-map-method-with-example/](https://www.geeksforgeeks.org/scala-stack-map-method-with-example/)

在 Scala `Stack class`中， **map()** 方法通过对给定堆栈的所有元素应用一个函数来构建一个新堆栈。

> **方法定义:** def 贴图【B】(f:(A)=>B):叠加【B】
> 
> **返回类型:**应用给定函数后返回包含所有元素的新堆栈。

**示例#1:**

```scala
// Scala program of map() 
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
        val s1 = Stack(5, 3, 2, 7, 6, 1) 

        // Print the stack 
        println(s1) 

        // Applying map method  
        val result = s1.map(x => x*x)

        // Display output 
        print("New stack after squaring all elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 3, 2, 7, 6, 1)
New stack after squaring all elements: Stack(25, 9, 4, 49, 36, 1)

```

**例 2:**

```scala
// Scala program of map() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5) 

        // Print the stack 
        println(s1) 

        // Applying map method  
        val result = s1.map(x => x/2)

        // Display output 
        print("New queue after dividing all elements by 2: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
New queue after dividing all elements by 2: Stack(0, 1, 1, 3, 3, 2)

```