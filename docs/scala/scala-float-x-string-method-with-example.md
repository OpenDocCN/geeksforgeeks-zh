# Scala Float +(x: String)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-x-string-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-string-method-with-example/)

使用 **+(x: String)** 方法返回指定的浮点值和字符串值之和。在这里，字符串被添加到指定浮点值的末尾。

> **方法定义:** (Float_Value)。+(字符串值)
> 
> **返回类型:**返回指定的浮点值和字符串值之和。

**示例#1:**

```scala
// Scala program of Float +(x: String)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: String) function
        val result = (6.0).+("GFG")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6.0GFG

```

**例 2:**

```scala
// Scala program of Float +(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Byte) function
        val result = (100.0).+("Geeks")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
100.0Geeks

```