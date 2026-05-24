# Scala Char %(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-char-method-with-example-12/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-12/)

使用 **%(x: Char)** 方法来寻找所述字符值除以 Char 类型的“x”的余数。

> **方法定义:** def %(x: Char): Int
> 
> 返回类型:返回 Int。

**示例:1#**

```scala
// Scala program of %(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Char) method 
val result = 'E'.%('C')

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
2

```

**示例:2#**

```scala
// Scala program of %(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Char) method
val result = 'B'.%('A')

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
1

```