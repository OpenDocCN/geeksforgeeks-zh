# Scala Map last()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-last-method-with-example/](https://www.geeksforgeeks.org/scala-map-last-method-with-example/)

使用 **last()** 方法返回地图的最后一个元素。

> **方法定义:**定义最后:(A，B)
> 
> **返回类型:**返回地图的最后一个元素。

下面是 Map last()方法的示例。
**例 1:**

```scala
// Scala program of last()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying last method
        val result = m1.last

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
(cs, 2)

```

这里，在地图的三个元素中，返回地图的第三个元素。
**例 2:**

```scala
// Scala program of last()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5)

        // Applying last method
        val result = m1.last

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
(geeks, 5)

```