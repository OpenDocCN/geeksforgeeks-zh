# Scala Map take()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-take-method-with-example/](https://www.geeksforgeeks.org/scala-map-take-method-with-example/)

利用 **take()** 方法选择地图的前 n 个元素。

> **方法定义:** def take(n: Int): Map[A，B]
> 
> **返回类型:**返回地图的前 n 个元素。

**示例#1:**

```scala
// Scala program of take()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying take method
        val result = m1.take(2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks, 4 -> for)

```

**例 2:**

```scala
// Scala program of take()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying take method
        val result = m1.take(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks, 4 -> for, 2 -> cs)

```