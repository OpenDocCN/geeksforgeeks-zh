# Scala Long *(x: Int)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-int-method-10/](https://www.geeksforgeeks.org/scala-long-x-int-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x: Long)** 方法返回指定的 Long 值和 Int 值的乘积。

> **方法定义–**def *(x:Int)
> 
> **返回–**返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Int) function
        val result = (15.toLong).*(5:Int)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
75
```

**例 2:**

```scala
// Scala program to explain working of
// Long *(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Int) function
        val result = (160.toLong).*(5:Int)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
800
```