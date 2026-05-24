# Scala Double %(x: Int)法

> 原文:[https://www.geeksforgeeks.org/scala-double-x-int-method-6/](https://www.geeksforgeeks.org/scala-double-x-int-method-6/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。当给定的 Double 值除以 Int 值时，使用 **%(x: Int)** 方法返回余数。

> **方法定义–**def %(x:Int)
> 
> 返回–返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double %(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Int) function
        val result = (10.021550.toDouble ).%(3:Int)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
1.0215499999999995

```