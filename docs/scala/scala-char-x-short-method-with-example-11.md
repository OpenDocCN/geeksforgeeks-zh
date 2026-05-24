# 斯卡拉查尔！=(x:短)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-short-method-with-example-11/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-11/)

**！=(x: Short)** 方法用于检查所述字符值是否不等于“x”。而‘x’是 Short 类型。

> **方法定义:** def！=(x: Short): Boolean
> 
> **返回类型:**如果所述字符值不等于‘x’，则返回 true，否则返回 false。

**示例:1#**

```scala
// Scala program of !=(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Short) method 
val result = 'E'.!=(1000)

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
// Scala program of !=(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Short) method
val result = 'B'.!=(-1000)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
true

```