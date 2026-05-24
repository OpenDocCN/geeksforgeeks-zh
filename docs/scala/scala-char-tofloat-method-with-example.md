# Scala Char toFloat()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-tofloat-method-with-example/](https://www.geeksforgeeks.org/scala-char-tofloat-method-with-example/)

**toFloat()** 方法用于将指定字符转换为浮点或浮点类型的 ASCII 值。

> **方法定义:**定义为浮动:浮动
> 
> **返回类型:**返回 float 类型对应字母的 Float 或 ASCII 值。

**例:1#**

```scala
// Scala program of toFloat()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toFloat method
        val result = 'A'.toFloat

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
65.0

```

**例:2#**

```scala
// Scala program of toFloat()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toFloat method
        val result = '7'.toFloat

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
55.0

```