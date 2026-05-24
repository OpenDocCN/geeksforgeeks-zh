# Scala TreeSet 积()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-product-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-product-method-with-example/)

利用**乘积()**方法返回树集合所有元素的乘积。

> **方法定义:**定义产品:甲
> 
> **返回类型:**返回树集合所有元素的乘积。

**示例#1:**

```scala
// Scala program of product() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying product method  
        val result = t1.product

        // Displays output  
        print("Product of all elements of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Product of all elements of the TreeSet: 120

```

**例 2:**

```scala
// Scala program of product() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(3, 7, 5, 2)  

        // Print the TreeSet 
        println(t1) 

        // Applying product method  
        val result = t1.product

        // Displays output  
        print("Product of all elements of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(2, 3, 5, 7)
Product of all elements of the TreeSet: 210

```