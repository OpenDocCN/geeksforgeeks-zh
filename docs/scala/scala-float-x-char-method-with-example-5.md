# Scala Float -(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-char-method-with-example-5/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example-5/)

利用 **-(x: Char)** 方法返回指定浮点值和 Char 值的差值。这里的字符值只是指定字符的 ASCII 值。

> **方法定义:** (Float_Value)。-(字符值)
> 
> **返回类型:**返回指定的浮点值和字符值的差值。

**示例#1:**

```scala
// Scala program of Float -(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Char) function
        val result = (100.0).-('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35.0

```

**例 2:**

```scala
// Scala program of Float -(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Char) function
        val result = (70.0).-('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
4.0

```