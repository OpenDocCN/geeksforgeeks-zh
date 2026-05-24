# Scala Char isValidShort()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is valid short-method-with-example/](https://www.geeksforgeeks.org/scala-char-isvalidshort-method-with-example/)

使用 **isValidShort()** 方法来查找所述字符是否在 Short 类型的范围内。

> **方法定义:** def isValidShort:布尔值
> 
> **返回类型:**如果所述字符在短类型范围内，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isValidShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidShort() method 
        val result = ('\u9999').isValidShort

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
// Scala program of isValidShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidShort() method
        val result = '\u0113'.isValidShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```