# 斯卡拉查尔！=(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-char-method-with-example-11/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-11/)

**！=(x: Char)** 方法用于检查所述字符值是否不等于“x”。“x”是 Char 类型。

> **方法定义:** def！=(x: Char):布尔值
> 
> **返回类型:**如果所述字符值不等于‘x’，则返回真，否则返回假。

**示例:1#**

```scala
// Scala program of !=(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Char) method 
val result = 'E'.!=('C')

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
// Scala program of !=(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Char) method
val result = 'B'.!=('B')

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
false

```