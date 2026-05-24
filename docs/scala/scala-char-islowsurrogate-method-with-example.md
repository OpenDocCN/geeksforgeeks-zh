# Scala Char islowSuperation()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-islowsurrogate-method-with-example/](https://www.geeksforgeeks.org/scala-char-islowsurrogate-method-with-example/)

**ISloSuperation()**方法用于查找所述字符值是否是 Unicode 低代理代码单元。这些值本身并不表示字符，而是用于表示 UTF-16 编码中的补充字符。

> **方法定义:**def IsLowSuperation:布尔值
> 
> **返回类型:**如果指定的字符是低代理，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isLowSurrogate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLowSurrogate() method 
        val result = '\udc28'.isLowSurrogate

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
// Scala program of isLowSurrogate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLowSurrogate() method
        val result = ('a').isLowSurrogate

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```