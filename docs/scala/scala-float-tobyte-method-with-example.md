# Scala Float toByte()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-to byte-method-with-example/](https://www.geeksforgeeks.org/scala-float-tobyte-method-with-example/)

利用 **toByte()** 方法将指定的数字转换为 Byte 数据类型值。字节数据类型的范围是从-128 到 127。

> **方法定义:**(数字)。toByte
> 
> **返回类型:**返回转换后的字节数据类型值。

**示例#1:**

```scala
// Scala program of Float toByte()
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
// Scala program of Float toByte()
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