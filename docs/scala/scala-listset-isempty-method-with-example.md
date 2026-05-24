# Scala ListSet isEmpty()方法示例

> 原文:[https://www . geesforgeks . org/Scala-listset-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-listset-isempty-method-with-example/)

在 Scala ListSet 中，利用 isEmpty()方法检查 ListSet 是否为空。如果它是空的，它将返回真，否则返回假。

> ***方法定义:*** *定义:布尔*
> 
> ***返回类型:*** *如果列表集不包含任何元素，则返回 rue，否则返回 false。*

***例 1:***

```scala
// Scala program of isEmpty() 
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
        val result = m1.isEmpty

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
        val m1 = ListSet()

        // Applying filter method 
        val result = m1.isEmpty

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
true

```