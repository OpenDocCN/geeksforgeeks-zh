# 斯卡拉产品图值

> 原文:[https://www.geeksforgeeks.org/scala-product-map-values/](https://www.geeksforgeeks.org/scala-product-map-values/)

在 Scala 中，地图元素的**乘积**可以利用*折叠*方法来完成。

> **语法:** m1.foldLeft(1)(_*_。_1)
> 
> 这里，m1 用于地图，foldLeft 是一种为产品取初始值 1 的方法。它将采用以前的结果，并将其乘以下一个地图键值。*并使用 1 作为初始值，以获得值的乘积。
> 
> **返回类型:**返回地图所有元素的乘积。

**示例#1:**

```scala
// Scala program of product()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 2 -> "for", 4 -> "for")

        // Applying product method
        val result = m1.foldLeft(1)(_*_._1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
24

```

这里 *foldLeft* 方法中的一个是初始值。
**例 2:**

```scala
// Scala program of product()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying product method
        val result = m1.foldLeft(1)(_*_._1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
12

```