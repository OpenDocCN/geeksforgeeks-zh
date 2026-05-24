# Scala Char & (x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-int-method-with-example-16/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-16/)

利用 **& (x: Int)** 方法，逐位查找所述字符值的**和**以及 Int 类型的“x”。

> **方法定义:** def & (x: Int): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of &(x: Int)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Int) method 
val result = 'E'.&(12)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
4

```

**例:2#**

```scala
// Scala program of &(x: Int)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Int) method
val result = 'A'.&(66)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
64

```