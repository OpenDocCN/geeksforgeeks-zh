# Scala Char %(x: Short)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-short-method-with-example-12/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-12/)

使用 **%(x: Short)** 方法来寻找所述字符值除以 Short 类型的“x”的余数。

> **方法定义:** def %(x: Short): Int
> 
> 返回类型:返回 Int。

**示例:1#**

```scala
// Scala program of %(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Short) method 
val result = '\u5531'.%(1000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
809

```

**示例:2#**

```scala
// Scala program of %(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Short) method
val result = '\u1111'.%(-1000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
369

```