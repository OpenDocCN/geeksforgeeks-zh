# 位元组比例> (x: Char): Boolean

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-char-boolean-2/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。如果该值大于 x，则使用方法>(x:Char)方法返回 true，否则返回 false。

> **方法定义:**字节> (x: Char):布尔值
> **返回类型:**如果该值大于 x 则返回 true，否则返回 false。

示例#1:

```scala
// Scala program of Byte >(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte >(x: Char) function 
        val result = (64.toByte).>('C':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false
```

示例 2:

```scala
// Scala program of Byte >(x: Char)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte >(x: Char) function 
        val result = (125.toByte).>('G':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true
```