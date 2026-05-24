# Scala Char min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-min-method-with-example/](https://www.geeksforgeeks.org/scala-char-min-method-with-example/)

利用 **min()** 方法寻找两个指定字符的最小值。

> **方法定义:**定义最小值(即:Char): Char
> 
> **返回类型:**返回最小值的字符。

**例:1#**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying min() method 
        val result = ('F').min('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
A

```

**例:2#**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying min() method
        val result = ('a').min('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
A

```