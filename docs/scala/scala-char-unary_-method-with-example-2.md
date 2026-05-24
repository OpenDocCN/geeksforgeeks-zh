# Scala Char 一元 _-()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-unary _-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-unary_-method-with-example-2/)

利用**一元 _-()** 方法给出所述字符的否定值。

> **方法定义:** def 一元 _-: Int
> 
> **返回类型:**返回指定字符的负整数值。

**例:1#**

```scala
// Scala program of unary_-()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_- method
        val result = '9'.unary_-

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-57

```

**例:2#**

```scala
// Scala program of unary_-()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_- method
        val result = 'A'.unary_-

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-65

```