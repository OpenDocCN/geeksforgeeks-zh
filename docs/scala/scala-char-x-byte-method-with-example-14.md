# Scala Char *(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-14/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-14/)

使用 ***(x: Byte)** 方法来寻找所述字符值和类型 Byte 的“x”的乘积。

> **方法定义:** def *(x:字节):Int
> 
> **返回类型:**返回 Int。

**示例:1#**

```scala
// Scala program of *(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying *(x: Byte) method 
val result = 'A'.*(126)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
8190

```

**示例:2#**

```scala
// Scala program of *(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying *(x: Byte) method
val result = 'A'.*(-125)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
-8125

```