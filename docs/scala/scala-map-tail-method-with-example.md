# Scala Map tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-tail-method-with-example/](https://www.geeksforgeeks.org/scala-map-tail-method-with-example/)

利用 **tail()** 方法显示除第一个元素以外的所有地图元素。

> **方法定义:**定义尾部:地图【A，B】
> 
> **返回类型:**返回所述地图除第一个元素外的所有元素。

**示例#1:**

```scala
// Scala program of tail()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying tail method
        val result = m1.tail

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(4 -> for, 2 -> cs)

```

**例 2:**

```scala
// Scala program of tail()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 3 -> "geeks")

        // Applying tail method
        val result = m1.tail

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(4 -> for)

```