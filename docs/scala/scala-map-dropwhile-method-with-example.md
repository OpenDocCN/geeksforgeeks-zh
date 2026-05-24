# Scala Map dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-map-dropwhile-method-with-example/)

使用 **dropWhile()** 方法删除元素，直到满足所述条件。

> **方法定义:** def dropWhile(p: ((A，B))=>Boolean:Map[A，B]
> 
> **返回类型:**返回所述映射中第一个元素不满足谓词 p 的元素的最长后缀

**示例#1:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying dropWhile method
        val result = m1.dropWhile(z=>false) 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(geeks -> 5, for -> 3, cs -> 2)

```

**例 2:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying dropWhile method
        val result = m1.dropWhile(z=>true) 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```