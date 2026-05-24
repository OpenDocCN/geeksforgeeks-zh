# Scala ListSet filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-filter-method-with-example/](https://www.geeksforgeeks.org/scala-listset-filter-method-with-example/)

在 Scala ListSet 中，filter()方法用于选择满足所述谓词的 ListSet 的所有元素。

> ***方法定义:*** *def 过滤器(p: (A) = >布尔型:ListSet[A]*
> 
> ***返回类型:*** *它返回一个新的列表集，该列表集包含满足给定谓词的列表集的所有元素。*

***例 1:***

```scala
// Scala program of filter() 
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
        val result = m1.filter(_>2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
ListSet(3, 4, 5, 7)

```

***例 2:***

```scala
// Scala program of filter() 
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
        val result = m1.filter(_<1) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
ListSet()

```