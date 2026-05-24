# Scala ListSet sum()方法示例

> 原文:[https://www . geesforgeks . org/Scala-listset-sum-method-with-example/](https://www.geeksforgeeks.org/scala-listset-sum-method-with-example/)

在 Scala ListSet 中，sum()方法用于添加所述 ListSet 的所有元素。

> ***方法定义:*** def sum(num:数学。数值【B】):B
> ***返回类型:*** *返回列表集中所有元素的总和。*

***例 1:***

```scala
// Scala program of sum() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, 2, 3, 4, 5, 7) 

        // Applying sum method 
        val result = m1.sum 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
22

```

***例 2:***

```scala
// Scala program of sum() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, -2) 

        // Applying sum method 
        val result = m1.sum 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
-1

```