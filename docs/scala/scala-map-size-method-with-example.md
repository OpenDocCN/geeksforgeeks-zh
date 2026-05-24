# Scala 地图大小()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-size-method-with-example/](https://www.geeksforgeeks.org/scala-map-size-method-with-example/)

**大小()**用于查找所述映射中键值对的数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回地图中的元素个数。

**示例#1:**

```scala
// Scala program of size()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs")

        // Applying size method
        val result = m1.size

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```

**例 2:**

```scala
// Scala program of size()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 1 -> "for", 1 -> "cs")

        // Applying size method
        val result = m1.size

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
2

```