# Scala Char %(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-12/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-12/)

使用 **%(x: Byte)** 方法来寻找所述字符值除以 Byte 类型的“x”的余数。

> **方法定义:** def %(x: Byte): Int
> 
> 返回类型:返回 Int。

**示例:1#**

```scala
// Scala program of %(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Byte) method 
val result = 'E'.%(111)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
69

```

**示例:2#**

```scala
// Scala program of %(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Byte) method
val result = 'B'.%(-116)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
66

```