# Scala Float > =(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-char-method-with-example-11/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example-11/)

如果浮点值大于或等于指定的字符值，则使用 **> =(x: Char)** 方法返回真。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Float_Value)。> =(char_Value)
> **返回类型:**如果浮点值大于或等于指定的 char 值，则返回 true。

**示例#1:**

```scala
// Scala program of Float >=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Char) function
        val result = (100.0).>=('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of Float >=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Char) function
        val result = (10.0).>=('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```