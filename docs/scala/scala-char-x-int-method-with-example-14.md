# 斯卡拉查尔！=(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-int-method-with-example-14/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-14/)

**！=(x: Int)** 方法用于检查所述字符值是否不等于“x”。而“x”是 Int 类型的。

> **方法定义:** def！=(x: Int):布尔值
> 
> **返回类型:**如果指定的字符值不等于‘x’，则返回真，否则返回假。

**示例:1#**

```scala
// Scala program of !=(x: Int)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Int) method 
val result = 'E'.!=(34)

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
// Scala program of !=(x: Int)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying !=(x: Int) method
val result = 'B'.!=(66)

// Displays output
println(result)

   }
} 
```

**输出:**

```scala
false

```