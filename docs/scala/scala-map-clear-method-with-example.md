# Scala Map clear()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-clear-method-with-example/](https://www.geeksforgeeks.org/scala-map-clear-method-with-example/)

利用**清除()**方法清除地图。value clear 是 Scala . collection . mutatable . map[String，Int]的成员。

> **方法定义:** def clear(): Unit
> 
> 返回类型:返回空图。

**示例#1:**

```scala
// Scala program of clear()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a mutable map
        val m1 = scala.collection.mutable.Map("geeks" -> 5, 
                                    "for" -> 3, "geeks" -> 1)

        // Applying clear method
        val result = m1.clear()

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
()

```