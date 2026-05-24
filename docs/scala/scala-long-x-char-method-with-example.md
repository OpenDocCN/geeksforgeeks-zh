# 斯卡拉龙！=(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-long-x-char-method-with-example/](https://www.geeksforgeeks.org/scala-long-x-char-method-with-example/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。**！=(x: Char)** 方法用于检查给定的 Long 和 Char 值是否相等。

> **方法定义–**def！=(x: Char):布尔值
> 
> **返回–**如果该值不等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain working 
// of Long !=(x: Char) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) function
        val result = (66).toLong.!= ('B':Char)

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

```scala
// Scala program to explain working
// of Long !=(x: Char) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) function
        val result = 1186000000.toLong.!= ('Z':Char)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true
```