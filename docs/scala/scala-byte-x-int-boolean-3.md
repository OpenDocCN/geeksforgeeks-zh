# 位元组比例> (x: Int): Boolean

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-int-boolean-3/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。如果该值大于 x，则使用方法>(x:Int)方法返回 true，否则返回 false。

> **方法定义:**字节> (x: Int):布尔值
> **返回类型:**如果该值大于 x 则返回 true，否则返回 false。

示例#1:

```scala
// Scala program of Byte >(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte >(x: Int) function 
        val result = (64.toByte).>(12:Int) 

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
// Scala program of Byte >(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte >(x: Int) function 
        val result = (25.toByte).>(111:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false
```