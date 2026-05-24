# Scala Char %(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-double-method-with-example-10/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-10/)

利用 **%(x: Double)** 方法求所述字符值除以 Double 类型的“x”的余数。

> **方法定义:**def %(x:Double):Double
> 
> 返回类型:返回 Double。

**示例:1#**

```scala
// Scala program of %(x: Double)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Double) method 
val result = 'E'.%(10.4536)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
6.278400000000001

```

**示例:2#**

```scala
// Scala program of %(x: Double)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying %(x: Double) method
val result = 'B'.%(15.7644)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
2.9423999999999992

```