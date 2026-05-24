# Scala String intern()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-intern-method-with-example/](https://www.geeksforgeeks.org/scala-string-intern-method-with-example/)

**intern()** 方法用于检查字符串对象的规范表示。

> **方法定义:** String intern()
> **返回类型:**返回字符串对象的规范表示。

**例:1#**

```scala
// Scala program of int intern()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying intern method
        val result = "GeeksforGeeks, \n\tA CS portal.".intern()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
GeeksforGeeks,
A CS portal.

```

**例:2#**

```scala
// Scala program of int intern()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying intern method
        val result = "My name is Nidhi, \ni am an author.".intern()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
My name is Nidhi,
i am an author.

```