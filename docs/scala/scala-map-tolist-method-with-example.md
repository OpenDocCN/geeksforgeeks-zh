# Scala Map toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-to list-method-with-example/](https://www.geeksforgeeks.org/scala-map-tolist-method-with-example/)

利用 **toList()** 方法在列表中显示地图的元素。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**返回列表中地图的所有元素。

**示例#1:**

```scala
// Scala program of toList()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toList method
        val result = m1.toList

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List((3, geeks), (4, for), (2, cs))

```

**例 2:**

```scala
// Scala program of toList()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toList method
        val result = m1.toList

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List((3, geeks), (4, for))

```