# Scala Int & (x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-3/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-3/)

**& (x: Char)** 方法用于返回由 Char 值对指定 int 值进行按位 AND 运算的结果。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。& (Char_Value)
> **返回类型:**返回由字符值对指定的 int 值进行按位 AND 运算的结果。

**示例#1:**

```scala
// Scala program of Int &(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: Char) function
        val result = (100).&('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
64

```

**例 2:**

```scala
// Scala program of Int &(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: Char) function
        val result = (100).&('D')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
68

```