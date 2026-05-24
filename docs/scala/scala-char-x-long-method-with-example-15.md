# Scala Char %(x: Long)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-long-method-with-example-15/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-15/)

利用 **%(x: Long)** 方法求所述字符值除以 Long 类型的“x”的余数。

> **法定义:** def %(x: Long): Long
> 
> 返回类型:返回 Long。

**示例:1#**

```scala
// Scala program of %(x: Long)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Long) method 
val result = '\u5555'.%(10000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
1845

```

**示例:2#**

```scala
// Scala program of %(x: Long)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Long) method
val result = '\u5555'.%(100000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
21845

```