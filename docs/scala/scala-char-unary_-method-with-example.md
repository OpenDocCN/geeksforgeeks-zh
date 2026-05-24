# Scala Char 一元 _~()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-unary _-method-with-example/](https://www.geeksforgeeks.org/scala-char-unary_-method-with-example/)

利用**一元 _~()** 方法寻找所述字符的逐位否定值。

> **方法定义:** def 一元 _~: Int
> 
> **返回类型:**返回指定字符的逐位负值。

**例:1#**

```scala
// Scala program of unary_~()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_~ method
        val result = 'A'.unary_~

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-66

```

**例:2#**

```scala
// Scala program of unary_~()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying unary_~ method
        val result = 'B'.unary_~

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-67

```