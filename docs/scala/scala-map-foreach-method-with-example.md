# Scala Map foreach()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-foreach-method-with-example/](https://www.geeksforgeeks.org/scala-map-foreach-method-with-example/)

foreach()方法用于将给定的函数应用于地图的所有元素。

> **方法定义:**def foreach(f:(A，B))=>Unit:Unit
> 
> **返回类型:**它将给定的函数应用于地图的所有元素后，返回每个元素。

**示例#1:**

```scala
// Scala program of foreach()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs", 6 -> "geeks")

        // Applying foreach method and 
        // displaying output 
        val result = m1.foreach(x => println("key=" + x._1 + ", value=" + x._2))

    }
}
```

**输出:**

```scala
key=3, value=geeks
key=1, value=for
key=2, value=cs
key=6, value=geeks

```