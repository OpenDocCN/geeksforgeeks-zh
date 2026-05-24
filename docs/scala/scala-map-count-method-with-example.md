# Scala Map count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-count-method-with-example/](https://www.geeksforgeeks.org/scala-map-count-method-with-example/)

利用**计数()**方法对地图中的一对关键点进行计数。

> **方法定义:** def count(p: ((A，B))=>Boolean:Int
> 
> **返回类型:**它返回地图中满足给定谓词的键的数量。

**示例#1:**

```scala
// Scala program of count()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 5)

        // Applying count method
        val result = m1.count(z=>true)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
3

```