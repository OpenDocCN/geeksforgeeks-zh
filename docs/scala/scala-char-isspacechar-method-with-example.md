# Scala Char isSpaceChar()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-isspace char-method-with-example/](https://www.geeksforgeeks.org/scala-char-isspacechar-method-with-example/)

**isSpaceChar()** 方法用于检查所述字符是否为空格字符。

> **方法定义:** def isSpaceChar:布尔值
> 
> **返回类型:**如果所述字符是空格字符，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isSpaceChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isSpaceChar() method 
        val result = ('\u2028').isSpaceChar

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
// Scala program of isSpaceChar()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isSpaceChar() method
        val result = ('*').isSpaceChar

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```