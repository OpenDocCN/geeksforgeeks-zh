# Scala Map 应用()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-apply-method-with-example/](https://www.geeksforgeeks.org/scala-map-apply-method-with-example/)

**apply()** 用于在所述地图中搜索关键字。

> **方法定义:**m1 . apply(“key”)
> 
> 这里 m1 是地图。
> 
> **返回类型:**返回要搜索的关键字的值。

**示例#1:**

```scala
// Scala program of apply()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "geeks" -> 5)

        // Applying apply method
        val result = m1.apply("for") 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```

**例 2:**

```scala
// Scala program of apply()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "geeks" -> 1)

        // Applying apply method
        val result = m1.apply("geeks") 

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
1

```

这里，相同的键具有不同的值，因此返回最后一个键的值。