# Scala Char toByte()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-to byte-method-with-example/](https://www.geeksforgeeks.org/scala-char-tobyte-method-with-example/)

**toByte()** 方法用于将指定的字符转换为字节类型。

> **方法定义:** def toByte: Byte
> 
> **返回类型:**返回指定字符的字节数。

**例:1#**

```scala
// Scala program of toByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toByte method
        val result = 'A'.toByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
65

```

**例:2#**

```scala
// Scala program of toByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toByte method
        val result = 'a'.toByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
97

```