# Scala Stack toArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-to array-method-with-example/](https://www.geeksforgeeks.org/scala-stack-toarray-method-with-example/)

在 Scala `Stack class`中， **toArray()** 用于返回一个包含堆栈所有元素的数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**它返回一个由栈的所有元素组成的数组。

**示例#1:**

```scala
// Scala program of toArray() 
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

        // Applying toArray method  
        val result = s1.toArray

        // Display output 
        print("Elements in the array: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Elements in the array: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toArray() 
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

        // Applying toArray method  
        val result = s1.toArray

        // Display output 
        print("Elements in the array: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
Elements in the array: 5 2 13 7 1

```