# Scala ListSet count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-count-method-with-example/](https://www.geeksforgeeks.org/scala-listset-count-method-with-example/)

在 Scala ListSet 中，count()方法用于统计 ListSet 中满足规定谓词的元素数量。

> ***方法定义:*** *def 计数(p: (A) = >布尔型:ListSet[A]*
> 
> ***返回类型:*** *它返回列表集中满足给定谓词的元素数量的计数。*

***例 1:***

```scala
// Scala program of count() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating litset
        val m1 = ListSet(1, 2, 3, 4, 5, 7)

        // Applying filter method 
        val result = m1.count(_>2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
4

```

***例 2:***

```scala
// Scala program of count() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating litset
        val m1 = ListSet(1, 2, 3, 4, 5, 7)

        // Applying filter method 
        val result = m1.count(_<1) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
0

```