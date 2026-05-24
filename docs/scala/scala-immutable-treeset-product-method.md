# Scala 不可变 TreeSet 积()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-product-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-product-method/)

在 Scala 不可变树集类中，**乘积()**方法用于返回树集所有元素的乘积。

> **方法定义:**定义产品:甲
> 
> **返回类型:**返回树集合所有元素的乘积。

**示例#1:**

```scala
// Scala program of product() 
// method 

// Import TreeSet
import scala.collection.immutable._

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
import scala.collection.immutable._

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