# Scala Map dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-map-dropright-method-with-example/)

利用 **dropRight()** 方法删除最后的‘n’个元素。

> **方法定义:** def dropRight(n: Int):地图【A，B】
> 
> **返回类型:**返回地图除最后‘n’个元素外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 5)

        // Applying dropRight method
        val result = m1.dropRight(1)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(geeks -> 5, for -> 3)

```