# Scala Map mkString()方法，带一个开始、一个分隔符和一个带示例的结尾

> 原文:[https://www . geesforgeks . org/Scala-map-MK string-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-map-mkstring-method-with-a-start-a-separator-and-an-end-with-example/)

此方法与 **mkString()** 相同，但这里还增加了一个开始、一个分隔符和一个结束。

> **方法定义:** defmkString(开始:String，sep: String，结束:String): String
> 
> **返回类型:**它以字符串形式返回地图的元素，以及指定的开始、分隔符和结束。

**示例#1:**

```scala
// Scala program of mkString() method
// with a start, a separator and an
// end

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying mkString method 
        val result = m1.mkString(">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>geeks -> 5|for -> 3|cs -> 2--

```

**例 2:**

```scala
// Scala program of mkString() method
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

        // Applying mkString method 
        val result = m1.mkString(">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>geeks -> 5|for -> 3--

```