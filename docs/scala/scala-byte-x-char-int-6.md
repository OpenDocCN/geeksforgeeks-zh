# 位元组比例+(x: Char): Int

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-char-int-6/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法+(x:Char)方法用于返回该值与 x 的和。

> **方法定义:** Byte +(x: Char): Int
> **返回类型:**它返回这个值的和乘以 x。

示例#1:

```scala
// Scala program of Byte +(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte +(x: Char) function 
        val result = (156.toByte).+('C':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-33
```

示例 2:

```scala
// Scala program of Byte +(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte +(x: Char) function 
        val result = (121.toByte).+('G':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
192
```