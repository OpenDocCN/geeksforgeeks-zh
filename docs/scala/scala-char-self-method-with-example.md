# Scala Char self()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-self-method-with-example/](https://www.geeksforgeeks.org/scala-char-self-method-with-example/)

利用 **self()** 方法返回所述字符本身。

> **方法定义:**定义自身:字符
> 
> **返回类型:**返回 Char。

**例:1#**

```scala
// Scala program of self()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying self() method 
        val result = ('F').self

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
// Scala program of self()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying self() method
        val result = ('9').self

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
9

```