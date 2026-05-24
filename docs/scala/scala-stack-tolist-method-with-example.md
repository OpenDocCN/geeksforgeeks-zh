# Scala Stack toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-to list-method-with-example/](https://www.geeksforgeeks.org/scala-stack-tolist-method-with-example/)

在 Scala `Stack class`中， **toList()** 方法用于返回包含堆栈所有元素的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个由栈的所有元素组成的列表。

**示例#1:**

```scala
// Scala program of toList() 
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

        // Applying toList method  
        val result = s1.toList

        // Display output 
        print("Elements in the list: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Elements in the list: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toList() 
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

        // Applying toList method  
        val result = s1.toList

        // Display output 
        print("Elements in the list: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
Elements in the list: 5 2 13 7 1

```