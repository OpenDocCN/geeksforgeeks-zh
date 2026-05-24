# 标量和映射值

> 原文:[https://www.geeksforgeeks.org/scala-sum-map-values/](https://www.geeksforgeeks.org/scala-sum-map-values/)

在 Scala 中，地图元素的**和**可以利用 *foldLeft* 方法完成。

> **语法:** m1.foldLeft(0)(_+_。_1)
> 
> 这里，m1 用于 Map，foldLeft 是一个取初始值零的方法。它将采用以前的结果，并将其添加到下一个地图键值。
> 
> **返回类型:**返回地图所有元素的总和。

**示例#1:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs")

        // Applying sum method
        val result = m1.foldLeft(0)(_+_._1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
6

```

这里 *foldLeft* 方法中的零为初始值。
**例 2:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 1 -> "for", 1 -> "for")

        // Applying sum method
        val result = m1.foldLeft(0)(_+_._1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
4

```