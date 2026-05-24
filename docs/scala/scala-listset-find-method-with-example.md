# Scala ListSet find()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-find-method-with-example/](https://www.geeksforgeeks.org/scala-listset-find-method-with-example/)

在 Scala ListSet 中，利用 find()方法找到满足给定谓词的 ListSet 的第一个元素。

> ***方法定义:****def find(p:(A)=>Boolean:选项【A】*
> 
> ***返回类型:*** *它返回满足给定谓词的列表集的第一个元素。*

***例 1:***

```scala
// Scala program of find() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating ListSet

        val m1 = ListSet(1, 2, 3) 

        // Applying find method 
        val result = m1.find(_>1) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Some(3)

```

***例 2:***

```scala
// Scala program of find() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating ListSet

        val m1 = ListSet(1, 2, 3) 

        // Applying find method 
        val result = m1.find(_<1) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
None

```