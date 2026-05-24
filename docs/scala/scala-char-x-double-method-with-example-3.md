# Scala Char /(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-double-method-with-example-3/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-3/)

利用 **/(x: Double)** 方法求出所述字符值与 Double 类型的‘x’的商。

> **方法定义:** def /(x: Double): Double
> 
> **返回类型:**返回 Double。

**例:1#**

```scala
// Scala program of /(x: Double)
// method

// Creating object
object GfG 
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Double) method 
        val result = 'A'./(111.65785)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.5821355148787121

```

**例:2#**

```scala
// Scala program of /(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Double) method
        val result = 'D'./(9845.65785)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.006906597917172188

```