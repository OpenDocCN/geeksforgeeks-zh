# Scala String getBytes()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-getbytes-method-with-example/](https://www.geeksforgeeks.org/scala-string-getbytes-method-with-example/)

**getBytes()** 方法用于将指定的字符串编码成一系列字节，然后将其存储到新的字节数组中。此外，这里使用了平台默认字符集。

> **方法定义:**字节 getBytes()
> T3】返回类型:它返回一个存储一系列字节的新字节数组。

**示例#1:**

```scala
// Scala program of getBytes()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getBytes method
        val result = "Nidhi".getBytes()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
[B@506e1b77

```

**例 2:**

```scala
// Scala program of getBytes()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getBytes method
        val result = " ".getBytes()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
[B@506e1b77

```