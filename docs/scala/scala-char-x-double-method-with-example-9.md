# 斯卡拉查尔！=(x: Double)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-double-method-with-example-9/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-9/)

**！=(x: Double)** 方法用于检查所述字符值是否不等于“x”。“x”是 Double 类型。

> **方法定义:** def！=(x: Double): Boolean
> 
> **返回类型:**如果所述字符值不等于‘x’，则返回 true，否则返回 false。

**示例:1#**

```scala
// Scala program of !=(x: Double)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Double) method 
val result = 'E'.!=(79.1234)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
true

```

**示例:2#**

```scala
// Scala program of !=(x: Double)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Double) method
val result = 'B'.!=(66.0000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
false

```