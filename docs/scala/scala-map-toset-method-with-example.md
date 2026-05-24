# Scala Map toSet()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-toset-method-with-example/](https://www.geeksforgeeks.org/scala-map-toset-method-with-example/)

**toSet()** 方法用于显示 Scala 地图中的集合。

> **方法定义:**定义:设置【A】
> 
> **返回类型:**从指定的地图返回一组。

**示例#1:**

```scala
// Scala program of toSet()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toSet method
        val result = m1.toSet

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set((3, geeks), (4, for))

```

**例 2:**

```scala
// Scala program of toSet()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toSet method
        val result = m1.toSet

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set((3, geeks), (4, for), (2, cs))

```