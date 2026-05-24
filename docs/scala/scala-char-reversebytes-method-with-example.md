# Scala Char reverseBytes()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-reverse bytes-method-with-example/](https://www.geeksforgeeks.org/scala-char-reversebytes-method-with-example/)

**反转字节()**方法用于查找通过反转所述字符值中的字节序列而获得的值。

> **方法定义:**定义反转字节:字符
> 
> **返回类型:**返回 Char。

**例:1#**

```scala
// Scala program of reverseBytes()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying reverseBytes() method 
        val result = '\u4d00'.reverseBytes

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
M

```

**例:2#**

```scala
// Scala program of reverseBytes()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying reverseBytes() method
        val result = '\u5d00'.reverseBytes

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
]

```