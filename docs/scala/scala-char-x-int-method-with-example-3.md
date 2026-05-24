# Scala Char ^(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-int-method-with-example-3/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-3/)

**^(x: Int)** 方法被用来在自变量列表中找到所述字符和类型整数的给定“x”的逐位异或。

> **方法定义:**def ^(x: int:int
> 
> **返回类型:**返回指定字符和给定整数类型“x”的逐位异或。

**例:1#**

```scala
// Scala program of ^(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Int) method 
        val result = 'B'.^(1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
67

```

**例:2#**

```scala
// Scala program of ^(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Int) method
        val result = 'B'.^(20)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
86

```