# Scala Float toShort()方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-to short-method-with-example/](https://www.geeksforgeeks.org/scala-float-toshort-method-with-example/)

利用 **toShort()** 方法将指定的数字转换为短数据类型值。字节数据类型的范围是从-32，768 到 32，767

> **方法定义:**(数字)。toShort
> 
> **返回类型:**返回转换后的短数据类型值。

**示例#1:**

```scala
// Scala program of Float toShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toShort method
        val result = (199).toShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
199

```

**例 2:**

```scala
// Scala program of Float toShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toShort method
        val result = (32799).toShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-32737

```