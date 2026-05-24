# Scala Map mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-map-mkstring-method-with-example/)

使用 **mkString()** 方法将地图的元素表示为字符串。

> **方法定义:** def mkString: String
> 
> **返回类型:**以字符串形式返回地图的元素。

**示例#1:**

```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 6)

        // Applying mkString method 
        val result = m1.mkString

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
geeks -> 5for -> 3cs -> 6

```

**例 2:**

```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "for" -> 3)

        // Applying mkString method 
        val result = m1.mkString

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
geeks -> 5for -> 3

```