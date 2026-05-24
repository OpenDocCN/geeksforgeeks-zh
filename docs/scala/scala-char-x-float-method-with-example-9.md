# 斯卡拉查尔！=(x: Float)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-float-method-with-example-9/](https://www.geeksforgeeks.org/scala-char-x-float-method-with-example-9/)

**！=(x: Float)** 方法用于检查所述字符值是否不等于“x”。“x”是浮点型的。

> **方法定义:** def！=(x: Float): Boolean
> 
> **返回类型:**如果所述字符值不等于‘x’，则返回 true，否则返回 false。

**示例:1#**

```scala
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Float) method 
val result = 'E'.!=(44.5)

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
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Float) method
val result = 'B'.!=(66.0)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
false

```