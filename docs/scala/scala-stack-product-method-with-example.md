# Scala Stack 积()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-product-method-with-example/](https://www.geeksforgeeks.org/scala-stack-product-method-with-example/)

在 Scala `Stack class`中，**乘积()**方法用于返回堆栈中所有元素的乘积。

> **方法定义:**定义产品:甲
> 
> **返回类型:**返回栈中所有元素的乘积。

**示例#1:**

```scala
// Scala program of product() 
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

        // Applying product method  
        val result = s1.product

        // Display output 
        print("Product of all the elements of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Product of all the elements of the stack: 24

```

**例 2:**

```scala
// Scala program of product() 
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
        val s1 = Stack(5, 2, 3, 7) 

        // Print the stack 
        println(s1) 

        // Applying product method  
        val result = s1.product

        // Display output 
        print("Product of all the elements of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 3, 7)
Product of all the elements of the stack: 210

```