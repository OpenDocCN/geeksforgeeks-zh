# Scala 地图克隆()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-clone-method-with-example/](https://www.geeksforgeeks.org/scala-map-clone-method-with-example/)

**克隆()**方法用于制作接收器对象的副本。值克隆是 Scala . collection . mutable . map[String，Int]的成员。

> **方法定义:** def 克隆():地图【A，B】
> 
> **返回类型:**返回所用地图的副本。

**示例#1:**

```scala
// Scala program of clone()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = scala.collection.mutable.Map("geeks" -> 5, "for" -> 3)

        // Applying clone method
        val result = m1.clone()

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(geeks -> 5, for -> 3)

```