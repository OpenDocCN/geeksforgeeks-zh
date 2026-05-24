# Scala Char & (x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-char-method-with-example-13/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-13/)

利用 **& (x: Char)** 方法逐位查找所述字符值的**和**以及 Char 类型的‘x’。

> **方法定义:** def & (x: Char): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of &(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Char) method 
val result = 'E'.&('e')

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
69

```

**例:2#**

```scala
// Scala program of &(x: Char)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Char) method
val result = 'A'.&('a')

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
65

```