# Scala Map taker right()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-map-takeright-method-with-example/)

利用 **takeRight()** 方法选择地图的最后 n 个元素。

> **方法定义:**def taker right(n:Int):地图[A，B]
> 
> **返回类型:**返回地图的最后 n 个元素。

**示例#1:**

```scala
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying takeRight method
        val result = m1.takeRight(2)

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
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying takeRight method
        val result = m1.takeRight(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks, 4 -> for, 2 -> cs)

```