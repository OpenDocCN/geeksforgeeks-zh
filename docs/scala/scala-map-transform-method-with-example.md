# Scala Map 变换()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-transform-method-with-example/](https://www.geeksforgeeks.org/scala-map-transform-method-with-example/)

利用**变换()**方法将地图的元素变换成可变地图。

> **方法定义:** def 变换(f: (K，V) = > V): Map.this.type
> 
> **返回类型:**它转换地图的所有元素，并将它们返回到可变地图中。

**示例#1:**

```scala
// Scala program of transform()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying transform method
        val result = m1.transform((key,value) => value.toUpperCase)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> GEEKS, 4 -> FOR, 2 -> CS)

```

**例 2:**

```scala
// Scala program of transform()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying transform method
        val result = m1.transform((key,value) => value.toUpperCase)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> GEEKS, 4 -> FOR)

```