# Scala Char to(end: Char，step: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-toend-char-step-char-method-with-example/](https://www.geeksforgeeks.org/scala-char-toend-char-step-char-method-with-example/)

**到(结束:Char，步骤:Char)** 方法用于返回从所述字符到“结束”的范围，该范围在参数列表中给出，并且在参数列表中也指定了一些“步骤”。

> **方法定义:**定义为(结束:字符，步骤:字符):包含[字符]
> 
> **返回类型:**返回范围。

**例:1#**

```scala
// Scala program of to()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Applying to() method 
        val result = 'A'.to('G', 2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
NumericRange(A, C, E, G)

```

**例:2#**

```scala
// Scala program of to()
// method
// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Applying to() method
        val result = ('0').to('9', 3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
NumericRange(0, 3, 6, 9)

```