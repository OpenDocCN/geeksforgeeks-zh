# 斯卡拉字节！=(x:浮点):布尔型

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-float-boolean-6/](https://www.geeksforgeeks.org/scala-byte-x-float-boolean-6/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法！=(x:Float)方法用于在值不等于指定值 x 时返回 true，否则返回 false。

> **方法定义:**字节！=(x: Float): Boolean
> **返回类型:**如果值不等于指定值则返回 true，否则返回 false。

示例#1:

```scala
// Scala program of Byte !=(x: Float) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte !=(x: Float) function 
        val result = (100.toByte).!=(50:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true
```

示例 2:

```scala
// Scala program of Byte !=(x: Float) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte !=(x: Float) function 
        val result = (100.toByte).!=(100:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false
```