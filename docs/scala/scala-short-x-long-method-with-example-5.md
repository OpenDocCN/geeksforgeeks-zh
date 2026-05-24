# Scala 短百分比(x:长)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-long-method-with-example-5/](https://www.geeksforgeeks.org/scala-short-x-long-method-with-example-5/)

使用 **%(x: Long)** 方法来求所述短值除以 Long 类型的“x”的余数。

> **方法定义:** def %(x: Long): Long
> 
> **返回类型:**返回 Long。

**例:1#**

```scala
// Scala program of %(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Long) method 
        val result = (995).%(10000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
995

```

**例:2#**

```scala
// Scala program of %(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Long) method
        val result = (1000).%(100000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1000

```