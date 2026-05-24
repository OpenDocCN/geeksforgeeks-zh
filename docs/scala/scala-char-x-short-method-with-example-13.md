# Scala Char & (x: Short)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-short-method-with-example-13/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-13/)

利用 **& (x: Short)** 方法逐位查找所述字符值的**和**以及 Short 类型的‘x’。

> **方法定义:** def & (x:短):Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of &(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Short) method 
val result = 'E'.&(1000)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
64

```

**例:2#**

```scala
// Scala program of &(x: Short)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Short) method
val result = 'A'.&(-999)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
1

```