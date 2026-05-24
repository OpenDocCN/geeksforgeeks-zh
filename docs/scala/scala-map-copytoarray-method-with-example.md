# Scala Map copyToArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-copy to array-method-with-example/](https://www.geeksforgeeks.org/scala-map-copytoarray-method-with-example/)

**复制到数组()**方法用于将映射的键对复制到数组。

> **方法定义:** def copyToArray(xs: Array[(A，B)]:Unit
> 
> **返回类型:**它将地图的关键点返回到一个数组中。

**示例#1:**

```scala
// Scala program of copyToArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Creating Array 
        val x: Array[Any] = Array(0, 0, 0, 0, 0) 

        // using 'copyToArray' method 
        m1.copyToArray(x) 

        // Displays keys copied in 
        // the Array 
        for(m2 <-x) 
        println(m2) 
    }
}
```

**输出:**

```scala
(geeks, 5)
(for, 3)
(cs, 2)
0
0

```