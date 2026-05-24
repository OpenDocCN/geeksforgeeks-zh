# Scala Char ishitespace()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-ishitespace-method-with-example/](https://www.geeksforgeeks.org/scala-char-iswhitespace-method-with-example/)

使用**ishitespace()**方法来查找所述字符是否用于给出空白。

> **方法定义:**def ishitespace:Boolean
> 
> **返回类型:**如果所述字符返回空白，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isWhitespace()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhitespace() method 
        val result = ('\t').isWhitespace

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
// Scala program of isWhitespace()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhitespace() method
        val result = ('A').isWhitespace

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```