# Scala Char ^(x: Short)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-short-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-2/)

**^(x:短)**方法被用来在自变量列表中找到所述字符和短类型的给定“x”的逐位异或。

> **方法定义:** def ^(x:短:Int
> 
> **返回类型:**返回指定字符和给定短类型“x”的逐位异或。

**例:1#**

```scala
// Scala program of ^(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Short) method 
        val result = 'B'.^(10000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10066

```

**例:2#**

```scala
// Scala program of ^(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Short) method
        val result = 'B'.^(-10000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-10062

```