# Scala Float /(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-char-method-with-example-4/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example-4/)

利用 **/(x: Char)** 方法返回指定浮点值除以 Char 值时的商。这里的字符值只是字符的 ASCII 值。

> **方法定义:** (Float_Value)。/(字符值)
> 
> **返回类型:**返回指定浮点值除以字符值时的商。

**示例#1:**

```scala
// Scala program of Float /(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Char) function
        val result = (100.0)./('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1.5384615384615385

```

**例 2:**

```scala
// Scala program of Float /(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Char) function
        val result = (110.0)./('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1.6923076923076923

```