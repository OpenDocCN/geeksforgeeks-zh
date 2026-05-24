# Scala Long toChar()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-long-to char-method-with-example/](https://www.geeksforgeeks.org/scala-long-tochar-method-with-example/)

toChar()方法用于将指定的数字转换为字符值。这里指定的数字是 ASCII 值。

> **方法定义:**(数字)。托哈尔
> 
> **返回类型:**返回转换后的字符值。

**例 1:**

```scala
// Scala program of Long toChar()
// method

// Creating object
object Test
{

    // Main method
    def main(args : Array[String])
    {

        // Implementing toChar method
        val res = (68).toChar

        // Displays output
        println(res)
    }
}
```

**输出:**

```scala
D
```

**例 2:**

```scala
// Scala program of Long toChar()
// method

// Creating object
object Test
{

    // Main method
    def main(args : Array[String])
    {

        // Implementing toChar method
        val res = (82).toChar

        // Displays output
        println(res)
    }
}
```

**输出:**

```scala
R
```