# Scala Char is validachar()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is valid char-method-with-example/](https://www.geeksforgeeks.org/scala-char-isvalidchar-method-with-example/)

**是有效字符()**方法，用于查找所述字符是否在字符类型的范围内。

> **方法定义:**def is validachar:布尔值
> 
> **返回类型:**如果所述字符在字符类型范围内，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isValidChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidChar() method 
        val result = ('F').isValidChar

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
// Scala program of isValidChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidChar() method
        val result = ('\n').isValidChar

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```