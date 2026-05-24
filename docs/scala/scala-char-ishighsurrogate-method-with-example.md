# Scala Char IshighSuperation()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-ishihsurrogate-method-with-example/](https://www.geeksforgeeks.org/scala-char-ishighsurrogate-method-with-example/)

使用**IshighSuperation()**方法来查找所述字符值是否是 Unicode 高替代代码单元。这些值本身并不表示字符，而是用于表示 UTF-16 编码中的补充字符。

> **方法定义:**定义 IshighSuperation:布尔值
> 
> **返回类型:**如果指定的字符是高代理，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isHighSurrogate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isHighSurrogate() method 
        val result = ('\ud8b4').isHighSurrogate

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
// Scala program of isHighSurrogate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isHighSurrogate() method
        val result = ('\u0555').isHighSurrogate

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```