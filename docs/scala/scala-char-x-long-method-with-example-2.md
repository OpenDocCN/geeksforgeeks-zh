# Scala Char ^(x:长)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-long-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-2/)

**^(x:长)**方法被用来在自变量列表中找到所述字符和类型长的给定“x”的逐位异或。

> **方法定义:** def ^(x:龙):长
> 
> **返回类型:**返回指定字符和给定长类型“x”的逐位异或。

**例:1#**

```scala
// Scala program of ^(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Long) method 
        val result = 'B'.^(100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
100066

```

**例:2#**

```scala
// Scala program of ^(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Long) method
        val result = 'B'.^(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-100062

```