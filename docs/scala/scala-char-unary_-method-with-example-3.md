# Scala Char 一元 _+()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-unary _-method-with-example-3/](https://www.geeksforgeeks.org/scala-char-unary_-method-with-example-3/)

**一元 _+()** 方法用于将指定字符转换为其值，无需任何修改。

> **方法定义:** def 一元 _+: Int
> 
> **返回类型:**返回指定字符的整数值。

**例:1#**

```scala
// Scala program of unary_+()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_+ method
        val result = '9'.unary_+

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
57

```

**例:2#**

```scala
// Scala program of unary_+()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_+ method
        val result = 'A'.unary_+

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
65

```