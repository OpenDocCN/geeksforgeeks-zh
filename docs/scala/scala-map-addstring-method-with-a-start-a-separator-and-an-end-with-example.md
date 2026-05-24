# Scala Map addString()方法，带开始、分隔符和结尾，示例为

> 原文:[https://www . geesforgeks . org/Scala-map-addstring-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-map-addstring-method-with-a-start-a-separator-and-an-end-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个开始、一个分隔符和一个结束。

> **方法定义:** def addString(sb:可变。StringBuilder，开始:String，sep: String，结束:String):可变。StringBuilder
> 
> 其中， *sep* 是所述的分隔符。
> 
> **返回类型:**返回字符串生成器中的地图元素，这里还包括一个开始、一个分隔符和一个结束。

**示例#1:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 3)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), ">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>geeks -> 5|for -> 3|cs -> 3--

```

**例 2:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "for" -> 3)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), ">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
>>>geeks -> 5|for -> 3--

```

所以，这里删除了相同的键。