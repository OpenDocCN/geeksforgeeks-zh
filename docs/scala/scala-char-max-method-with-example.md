# Scala Char max()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-max-method-with-example/](https://www.geeksforgeeks.org/scala-char-max-method-with-example/)

利用 **max()** 方法寻找两个指定字符的最大值。

> **方法定义:** def max(即:Char): Char
> 
> **返回类型:**返回最大值的字符。

**例:1#**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying max() method 
        val result = ('F').max('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
F

```

**例:2#**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying max() method
        val result = ('a').max('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
a

```