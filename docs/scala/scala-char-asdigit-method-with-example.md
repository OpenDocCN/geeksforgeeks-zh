# Scala Char asDigit()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-as digit-method-with-example/](https://www.geeksforgeeks.org/scala-char-asdigit-method-with-example/)

**asDigit()** 方法用于以数字的形式表示字符。

> **方法定义:**定义为数字:整数
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of asDigit()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying asDigit() method 
        val result = 'A'.asDigit

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10

```

**例:2#**

```scala
// Scala program of asDigit()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying asDigit() method
        val result = 'E'.asDigit

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
14

```