# Scala Map max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-max-method-with-example/](https://www.geeksforgeeks.org/scala-map-max-method-with-example/)

利用 **max()** 方法寻找地图的最大元素。

> **方法定义:** def 最大值:(A，B)
> 
> **返回类型:**返回地图最大的元素。

**示例#1:**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying max method 
        val result = m1.max

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(geeks, 5)

```

**例 2:**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "geeks" -> 6)

        // Applying max method 
        val result = m1.max

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(geeks, 6)

```