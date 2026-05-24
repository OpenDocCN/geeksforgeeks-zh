# 带分隔符的 Scala List mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-MK string-method-with-a-separator-with-example/](https://www.geeksforgeeks.org/scala-list-mkstring-method-with-a-separator-with-example/)

**mkString()** 方法用于显示字符串中的所有列表元素以及分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它返回一个字符串中的所有列表元素以及一个分隔符。

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
        // Creating a list
        val m1 = List(2, 3, 5, 7, 8)

        // Applying mkString method
        val result = m1.mkString("*")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2*3*5*7*8

```

**例:2#**

```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 5)

        // Applying mkString method
        val result = m1.mkString("_")

        // Displays output
        println(result)

    }
} 

```

**Output:**

```scala
2_3_5_7_5

```