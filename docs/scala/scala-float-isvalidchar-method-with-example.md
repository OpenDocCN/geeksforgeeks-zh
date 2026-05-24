# Scala Float is validachar()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-is validachar-method-with-example/](https://www.geeksforgeeks.org/scala-float-isvalidchar-method-with-example/)

如果指定的数字为零或在 scala 的范围内，则使用**is validachar()**方法返回 true。Char MinValue 和 MaxValue 否则返回 false。

> **方法定义:** (Float_Number)。isValidChar
> 
> **返回类型:**如果指定的数字为零或在标量范围内，则返回真。Char MinValue 和 MaxValue 否则返回 false。

**示例#1:**

```scala
// Scala program of Float isValidChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidChar method
        val result = (0).isValidChar

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
// Scala program of Float isValidChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidChar method
        val result = (5.9).isValidChar

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```