# Scala Map 过滤器()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-filter-method-with-example/](https://www.geeksforgeeks.org/scala-map-filter-method-with-example/)

**过滤器()**方法用于选择满足所述谓词的地图的所有元素。

> **方法定义:** def 过滤器(p: ((A，B))= >布尔型:map[A，B]
> 
> **返回类型:**它返回一个由满足给定谓词的 Map 的所有元素组成的新 Map。

**示例#1:**

```scala
// Scala program of filter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3)

        // Applying filter method
        val result = m1.filter(x => x._1 == "geeks" && x._2 == 5)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(geeks -> 5)

```