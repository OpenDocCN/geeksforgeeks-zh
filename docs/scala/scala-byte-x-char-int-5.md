# 位元组比例^(x: Char): Int

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-char-int-5/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法^(x:Char)方法用于返回该值和 x 的按位异或

> **方法定义:**字节^(x:字符):Int
> **返回类型:**它返回这个值和 x 的按位异或。

示例#1:

```scala
// Scala program of Byte ^(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ^(x: Char) function 
        val result = (110.toByte).^('G':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
41
```

示例 2:

```scala
// Scala program of Byte ^(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ^(x: Char) function 
        val result = (128.toByte).^('C':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-61
```