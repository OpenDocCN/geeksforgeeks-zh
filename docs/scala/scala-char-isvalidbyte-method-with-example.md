# Scala Char isValidByte()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is valid byte-method-with-example/](https://www.geeksforgeeks.org/scala-char-isvalidbyte-method-with-example/)

**是有效字节()**方法，用于查找所述字符是否在字节类型的范围内。

> **方法定义:** def isValidByte: Boolean
> 
> **返回类型:**如果所述字符在字节类型的范围内，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isValidByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidByte() method 
        val result = ('F').isValidByte

        // Displays output
        println(result)

    }
} 

```

**Output:**

```scala
true

```

**例:2#**

```scala
// Scala program of isValidByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidByte() method
        val result = ('\u0555').isValidByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```