# 带分隔符的 Scala Map mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-map-mkstring-method-with-a-separator-with-example/)

此方法与 **mkString()** 方法相同，但此处还添加了一个分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它以字符串形式返回地图的元素以及它们之间的分隔符。

**示例#1:**

```scala
// Scala program of mkString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying mkString method 
        val result = m1.mkString("/")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
geeks -> 5/for -> 3/cs -> 2

```

**例 2:**

```scala
// Scala program of mkString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "geeks" -> 5)

        // Applying mkString method 
        val result = m1.mkString("/")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
geeks -> 5/for -> 3

```