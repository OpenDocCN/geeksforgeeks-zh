# Scala Char Isidentifier ignorable()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-isiidentifier ignorable-method-with-example/](https://www.geeksforgeeks.org/scala-char-isidentifierignorable-method-with-example/)

**IsidentifieReignorable()**方法用于确定所述字符是 Scala 标识符中的可忽略字符还是 Unicode 标识符中的可忽略字符。

> **方法定义:**定义 isIdentifierIgnorable:布尔值
> 
> **返回类型:**如果指定的字符是可忽略的控制字符，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isIdentifierIgnorable()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isIdentifierIgnorable() method 
        val result = ('\u0555').isIdentifierIgnorable

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
// Scala program of isIdentifierIgnorable()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isIdentifierIgnorable() method
        val result = ('\u000E').isIdentifierIgnorable

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```