# Scala 映射键()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-keys-method-with-example/](https://www.geeksforgeeks.org/scala-map-keys-method-with-example/)

**键()**方法被用来给地图的所有键一个迭代器。

> **方法定义:**定义键:可迭代【A】
> 
> **返回类型:**它返回一个遍历地图所有键的迭代器。

**示例#1:**

```scala
// Scala program of keys()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying keys method 
        val result = m1.keys

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
Set(geeks, for, cs)

```