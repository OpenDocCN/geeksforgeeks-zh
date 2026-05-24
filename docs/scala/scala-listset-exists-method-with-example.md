# Scala ListSet exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-listset-exists-method-with-example/](https://www.geeksforgeeks.org/scala-listset-exists-method-with-example/)

在 Scala ListSet 中，使用 exists()方法检查给定的谓词是否满足 ListSet 的元素。

> ***方法定义:*** *def 存在(p: (A) = >布尔:布尔*
> 
> ***返回类型:*** *如果所述谓词对列表集的某些元素成立，则返回真，否则返回假。*

***例 1:***

```scala
// Scala program of exists() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating Listset
        val m1 = ListSet(1, 2, 3, 4, 5, 7) 

        // Applying exists method 
        val result = m1.exists(_==9) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```

***例 2:***

```scala
// Scala program of exists() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating listset 
        val m1 = ListSet(1, 2, 3, 4, 5, 7) 

        // Applying exists method 
        val result = m1.exists(_>9) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```