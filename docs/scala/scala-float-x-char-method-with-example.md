# Scala Float ==(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-x-char-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example/)

如果浮点值等于字符值，则使用 **==(x: Char)** 方法返回真，否则返回假。这里的字符值只是指定字符的 ASCII 值。

> **方法定义:** (Float_Value)。==(字符值)
> 
> **返回类型:**如果浮点值等于字符值，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float ==(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Char) function
        val result = (100.0).==('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float ==(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Char) function
        val result = (65.0).==('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```