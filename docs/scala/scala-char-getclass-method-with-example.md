# Scala Char getClass()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-getclass-method-with-example/](https://www.geeksforgeeks.org/scala-char-getclass-method-with-example/)

**getClass()** 方法用于返回所述对象的运行时类表示。

> **方法定义:** def getClass(): Class[Char]
> 
> **返回类型:**返回所述对象的类。

**例:1#**

```scala
// Scala program of getClass()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getClass() method 
        val result = 'a'.getClass

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
char

```

**例:2#**

```scala
// Scala program of getClass()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getClass() method
        val result = '5'.getClass

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
char

```