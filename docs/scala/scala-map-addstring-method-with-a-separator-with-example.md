# 带分隔符的 Scala Map addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-add string-method-with-a-separator-with-example/](https://www.geeksforgeeks.org/scala-map-addstring-method-with-a-separator-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个分隔符。

> **方法定义:**def addString(b:StringBuilder，sep:String):StringBuilder
> 
> 其中， *sep* 为所述分隔符。
> 
> **返回类型:**它在字符串生成器中返回地图的元素，并且在地图的元素之间还添加了分隔符。

**示例#1:**

```scala
// Scala program of addString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying addString method
        // and a separator
        val result = m1.addString(new StringBuilder(), "_") 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
geeks -> 5_for -> 3_cs -> 2

```

**例 2:**

```scala
// Scala program of addString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "geeks" -> 2)

        // Applying addString method
        // and a separator
        val result = m1.addString(new StringBuilder(), "_") 

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
geeks -> 2_for -> 3

```

所以，这里删除了相同的键。