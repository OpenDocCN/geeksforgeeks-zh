# Scala Char toInt()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-to int-method-with-example/](https://www.geeksforgeeks.org/scala-char-toint-method-with-example/)

**toInt()** 方法用于将指定的字符转换为整数或其类型为 Int 的 ASCII 值。

> **方法定义:**定义为:Int
> 
> **返回类型:**返回 Int 类型对应字符的整数或 ASCII 值。

**例:1#**

```scala
// Scala program of toInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toInt method
        val result = 'A'.toInt

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
65

```

**例:2#**

```scala
// Scala program of toInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toInt method
        val result = '9'.toInt

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
57

```