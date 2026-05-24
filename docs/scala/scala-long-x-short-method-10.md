# Scala Long *(x: Short)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-short-method-10/](https://www.geeksforgeeks.org/scala-long-x-short-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x:短)**方法返回指定长值和短值的乘积。

> **方法定义–**def *(x:短)
> 
> **返回–**返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Short) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Short) function
        val result = (10.toLong).*(4:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
650
```

**例 2:**

```scala
// Scala program to explain working of
// Long *(x: Short) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Short) function
        val result = (150.toLong).*(5:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
10650
```