# Scala Char toShort()方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-to short-method-with-example/](https://www.geeksforgeeks.org/scala-char-toshort-method-with-example/)

**toShort()** 方法用于将指定的字符转换为 Short 类型。

> **方法定义:**定义为短:短
> 
> **返回类型:**返回做空。

**例:1#**

```scala
// Scala program of toShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toShort method
        val result = '\u5555'.toLong

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
21845

```

**例:2#**

```scala
// Scala program of toShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toShort method
        val result = '\u1111'.toShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
4369

```