# Scala Char & (x: Long)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-long-method-with-example-16/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-16/)

利用 **& (x: Long)** 方法，逐位查找所述字符值的**和**以及 Long 类型的‘x’。

> **方法定义:** def & (x:龙):龙
> 
> **返回类型:**返回 Long。

**例:1#**

```scala
// Scala program of &(x: Long)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Long) method 
val result = 'E'.&(100000L)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
0

```

**例:2#**

```scala
// Scala program of &(x: Long)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Long) method
val result = 'A'.&(-100000L)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
64

```