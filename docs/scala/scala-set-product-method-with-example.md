# Scala 集积()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-product-method-with-example/](https://www.geeksforgeeks.org/scala-set-product-method-with-example/)

利用**乘积()**方法求集合所有元素的乘积。

> **方法定义:**定义产品:甲
> 
> **返回类型:**返回集合所有元素的乘积。

**示例#1:**

```scala
// Scala program of product() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3) 

        // Applying product method 
        val result = s1.product

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
6

```

**例 2:**

```scala
// Scala program of product() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying product method 
        val result = s1.product

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
120

```