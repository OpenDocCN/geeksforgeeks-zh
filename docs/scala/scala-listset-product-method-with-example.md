# Scala ListSet 乘积()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-product-method-with-example/](https://www.geeksforgeeks.org/scala-listset-product-method-with-example/)

在 Scala ListSet 中，利用乘积()方法求所述 ListSet 元素的乘积。

> ***方法定义:*** *def 积(num: math。数字【B】):B*
> 
> ***返回类型:*** *返回指定列表集中所有元素的乘积。*

***例 1:***

```scala
// Scala program of size() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, 2, 3, 4, 5) 

        // Applying size method 
        val result = m1.size 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
5

```

***例 2:***

```scala
// Scala program of product() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, 8, -4, -5) 

        // Applying product method 
        val result = m1.product 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
160

```