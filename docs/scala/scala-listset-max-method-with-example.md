# Scala ListSet max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-listset-max-method-with-example/](https://www.geeksforgeeks.org/scala-listset-max-method-with-example/)

在 Scala ListSet 中，利用 max()方法寻找所述列表中所有元素中最大的元素。

> ***方法定义:****def max【B>:A】(隐含顺序:数学。订购【乙】):甲*
> 
> ***返回类型:*** *它返回指定列表集中所有元素中最大的一个。*

***例 1:***

```scala
// Scala program of min() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, 2, 3) 

        // Applying min method 
        val result = m1.max

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
3

```

***例 2:***

```scala
// Scala program of min() 
// method 
import scala.collection.immutable._
// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        val m1 = ListSet(1, 2, -3) 

        // Applying min method 
        val result = m1.max

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
2

```