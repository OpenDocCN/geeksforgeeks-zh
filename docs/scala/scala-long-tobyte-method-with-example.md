# Scala Long toByte()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-long-to byte-method-with-example/](https://www.geeksforgeeks.org/scala-long-tobyte-method-with-example/)

toByte()方法用于将指定的数字转换为 Byte 数据类型值。字节数据类型的范围是从-128 到 127。

> **方法定义:**(数字)。toByte
> 
> **返回类型:**返回转换后的字节数据类型值。

**例 1:**

```scala
// Scala program of Long toByte()
// method

// Creating object
object Test
{

    // Main method
    def main(args : Array[String])
    {

        // Implementing toByte method
        val res = (25).toByte

        // Displays output
        println(res)
    }
}
```

**输出:**

```scala
25
```

**例 2:**

```scala
// Scala program of Long toByte()
// method

// Creating object
object Test
{

    // Main method
    def main(args : Array[String])
    {

        // Implementing toByte method
        val res = (129).toByte

        // Displays output
        println(res)
    }
}
```

**输出:**

```scala
-127
```