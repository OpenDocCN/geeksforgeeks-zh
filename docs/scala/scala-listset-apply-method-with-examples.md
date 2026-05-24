# Scala Listset 应用()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-apply-method-with-examples/](https://www.geeksforgeeks.org/scala-listset-apply-method-with-examples/)

在 Scala 列表集中， **apply()** 方法用于检查列表集中是否存在给定的元素。

> ***方法定义:*** *最终定义应用(elem: A):布尔*
> 
> ***返回类型:*** *如果元素存在则为真，否则为假。*

***例 1:***

```scala
// Scala program of apply() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a listSet
        val m1 = ListSet(1, 3, 5, 2) 

        // Applying apply method 
        val res = m1.apply(3) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
true

```

***例 2:***

```scala
// Scala program of apply() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a listSet
        val m1 = ListSet(1, 3, 5, 2) 

        // Applying apply method 
        val res = m1.apply(3) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
true

```