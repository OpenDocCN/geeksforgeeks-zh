# Scala Int toByte()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-to byte-method-with-example/](https://www.geeksforgeeks.org/scala-int-tobyte-method-with-example/)

利用 **toByte()** 方法将指定的 int 数转换为 Byte 数据类型值。

> **方法定义:**(数字)。toByte
> 
> **返回类型:**返回转换后的字节数据类型值。

**示例#1:**

```scala
// Scala program of Int toByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toByte method
        val result = (66).toByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
66

```

**例 2:**

```scala
// Scala program of Int toByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toByte method
        val result = (129).toByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-127

```