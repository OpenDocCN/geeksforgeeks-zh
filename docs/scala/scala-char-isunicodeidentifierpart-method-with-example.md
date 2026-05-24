# Scala Char isnicodieidentifier part()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-isunicodeidentifier part-method-with-example/](https://www.geeksforgeeks.org/scala-char-isunicodeidentifierpart-method-with-example/)

使用**isunicodeidentifier part()**方法来查找所述字符是否是 Unicode 标识符的一部分，而不是第一个字符。例如:数字、字母、组合标记、连接标点符号(如“_”)、数字字母(如罗马数字字符)和无间距标记。

> **方法定义:**def isunicodeidentifier part:Boolean
> 
> **返回类型:**如果所述字符是 Unicode 标识符的一部分，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isUnicodeIdentifierPart()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isUnicodeIdentifierPart() method 
        val result = ('7').isUnicodeIdentifierPart

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
// Scala program of isUnicodeIdentifierPart()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isUnicodeIdentifierPart() method
        val result = ('_').isUnicodeIdentifierPart

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```