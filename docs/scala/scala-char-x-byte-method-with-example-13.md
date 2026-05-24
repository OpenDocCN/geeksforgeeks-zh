# Scala Char & (x: Byte)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-13/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-13/)

利用 **& (x: Byte)** 方法，逐位查找所述字符值的**和**以及 Byte 类型的‘x’。

> **方法定义:** def & (x:字节):Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of &(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Byte) method 
val result = 'E'.&(123)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
65

```

**例:2#**

```scala
// Scala program of &(x: Byte)
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying &(x: Byte) method
val result = 'A'.&(-121)

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
1

```