# Scala Char isLetter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is letter-method-with-example/](https://www.geeksforgeeks.org/scala-char-isletter-method-with-example/)

**isLetter()** 方法用于检查所述字符是否为字母。

> **方法定义:**定义属性:布尔型
> 
> **返回类型:**如果所述字符是字母，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isLetter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLetter method
        val result = '9'.isLetter

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例:2#**

```scala
// Scala program of isLetter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLetter method
        val result = 'g'.isLetter

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```