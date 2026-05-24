# Scala Float %(x: Char)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-char-method-with-example-8/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example-8/)

当给定的浮点值除以字符值时，使用 **%(x: Char)** 方法返回余数。这里的字符值只是指定字符的 ASCII 值。

> **方法定义:** (Float_Value)。%(字符值)
> 
> **返回类型:**当给定的浮点值除以字符值时，返回余数。

**示例#1:**

```scala
// Scala program of Float %(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Char) function
        val result = (65.0).%('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.0

```

**例 2:**

```scala
// Scala program of Float %(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Char) function
        val result = (100.0).%('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35.0

```