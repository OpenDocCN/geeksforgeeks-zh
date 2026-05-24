# Scala Char %(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-float-method-with-example-10/](https://www.geeksforgeeks.org/scala-char-x-float-method-with-example-10/)

使用 **%(x: Float)** 方法来寻找所述字符值除以 Float 类型的“x”的余数。

> **方法定义:** def %(x: Float): Float
> 
> 返回类型:返回 Float。

**示例:1#**

```scala
// Scala program of %(x: Float)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Float) method 
val result = 'E'.%(2.1)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
1.7999999999999972

```

**示例:2#**

```scala
// Scala program of %(x: Float)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Float) method
val result = 'B'.%(4.5)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
3.0

```