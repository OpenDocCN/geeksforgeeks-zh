# 短刻度< =(x: Char): Boolean

> 原文:[https://www.geeksforgeeks.org/scala-short-x-char-boolean/](https://www.geeksforgeeks.org/scala-short-x-char-boolean/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型

> **方法定义:** def < =(x: Char):布尔值
> **返回类型:**如果该值小于或等于 x，则返回 true，否则返回 false。

**示例#1:**

## 斯卡拉

```scala
// Scala program of Short <=(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Short <=(x: Char) function
        val result = (998.toShort).<=('G':Char)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```

**例 2:**

## 斯卡拉

```scala
// Scala program of Short <=(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Short <=(x: Char) function
        val result = (55.toShort).<=('V':Char)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```