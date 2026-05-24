# Scala Char toLong()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-tolong-method-with-example/](https://www.geeksforgeeks.org/scala-char-tolong-method-with-example/)

**toLong()** 方法用于将指定字符转换为 Long 或其类型为 Long 的 ASCII 值。

> **方法定义:**定义:龙
> 
> **返回类型:**返回 Long 类型对应字母的 Long 或 ASCII 值。

**例:1#**

```scala
// Scala program of toLong()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toLong method
        val result = '\u1155'.toLong

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
4437

```

**例:2#**

```scala
// Scala program of toLong()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toLong method
        val result = '\u1234'.toLong

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
4660

```