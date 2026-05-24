# Scala ListSet size()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-size-method-with-example/](https://www.geeksforgeeks.org/scala-listset-size-method-with-example/)

在 Scala ListSet 中，利用 size()方法找到所述 ListSet 的元素个数。

> ***方法定义:*** *def size(): Int*
> 
> ***返回类型:*** *返回指定列表集中的元素数量。*

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
        val m1 = ListSet(1, 2) 

        // Applying size method 
        val result = m1.size 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
2

```