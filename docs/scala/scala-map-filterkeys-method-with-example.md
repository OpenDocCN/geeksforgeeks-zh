# Scala Map filterKeys()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-filter keys-method-with-example/](https://www.geeksforgeeks.org/scala-map-filterkeys-method-with-example/)

**filterKeys()** 方法用于查找所有键满足给定谓词的对。

> **方法定义:**def filterKeys(p:(A)=>Boolean:Map[A，B]
> 
> **返回类型:**返回 Map 的所有“键值”对，其中，key 满足给定的谓词。

**示例#1:**

```scala
// Scala program of filterKeys()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map(5 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying filterKeys method
        val result = m1.filterKeys(_ > 2)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(5 -> geeks, 4 -> for)

```