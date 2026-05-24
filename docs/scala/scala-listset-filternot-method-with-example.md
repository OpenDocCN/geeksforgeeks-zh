# Scala ListSet filterNot()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-filter not-method-with-example/](https://www.geeksforgeeks.org/scala-listset-filternot-method-with-example/)

在 Scala ListSet 中，filterNot()方法用于选择 ListSet 中不满足规定谓词的所有元素。

> ***方法定义:****def filter not(p:(A)=>Boolean:ListSet[A]*
> 
> ***返回类型:*** *它返回一个新的列表集，该列表集包含列表集中不满足给定谓词的所有元素。*

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
        val result = m1.filterNot(_>2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
ListSet(1, 2)

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
        val result = m1.filterNot(_<1) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
ListSet(1, 2, 3, 4, 5, 7)

```