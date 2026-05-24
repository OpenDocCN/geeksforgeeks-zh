# Scala Map find()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-find-method-with-example/](https://www.geeksforgeeks.org/scala-map-find-method-with-example/)

**find()** 方法用于找到满足给定谓词的地图的第一个元素。

> **方法定义:** def find(p: ((A，B))=>Boolean:Option[(A，B)]
> 
> **返回类型:**返回满足给定谓词的映射的第一个元素。

**示例#1:**

```scala
// Scala program of find()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs")

        // Applying find method
        val result = m1.find(_._2 == "for")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Some((1, for))

```

因此，这里第二对是满足给定谓词的第一对，因此，返回第二对。
**例 2:**

```scala
// Scala program of find()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs", 6 -> "geeks")

        // Applying find method
        val result = m1.find(_._2 == "geeks")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Some((3, geeks))

```