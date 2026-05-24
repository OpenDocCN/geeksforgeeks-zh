# Scala Char toDouble()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-to double-method-with-example/](https://www.geeksforgeeks.org/scala-char-todouble-method-with-example/)

**toDouble()** 方法用于将指定字符转换为 Double 或其类型为 Double 的 ASCII 值。

> **方法定义:**定义为双:双
> 
> **返回类型:**返回 Double 类型对应字母的 Double 或 ASCII 值。

**例:1#**

```scala
// Scala program of toDouble()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toDouble method to uni-code representation of character
        val result = '\u0051'.toDouble

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
81.0

```

这里，' \u0051 '是 Q.
**的单码表示例:2#**

```scala
// Scala program of toDouble()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toDouble method
        val result = '\n'.toDouble 

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10.0

```