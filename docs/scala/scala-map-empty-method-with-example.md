# Scala Map 空()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-empty-method-with-example/](https://www.geeksforgeeks.org/scala-map-empty-method-with-example/)

利用**清空()**方法清空地图。

> **方法定义:** def 空:地图【A，B】
> 
> **返回类型:**返回空地图。

**示例#1:**

```scala
// Scala program of empty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying empty method
        val result = m1.empty

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```

**例 2:**

```scala
// Scala program of empty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an empty map
        val m1 = Map()

        // Applying empty method
        val result = m1.empty

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```