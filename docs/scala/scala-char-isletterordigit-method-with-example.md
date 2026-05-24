# Scala Char IsLatterOrdigit()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-isletterordigit-method-with-example/](https://www.geeksforgeeks.org/scala-char-isletterordigit-method-with-example/)

**isLetterOrDigit()** 方法用于检查所述字符是字母还是数字。

> **方法定义:**定义模式数字:布尔值
> 
> **返回类型:**如果所述字符是字母或数字，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isLetterOrDigit()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLetterOrDigit method
        val result = '9'.isLetterOrDigit

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
// Scala program of isLetterOrDigit()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLetterOrDigit method
        val result = 'g'.isLetterOrDigit

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```