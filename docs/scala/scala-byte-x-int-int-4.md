# 位元组比例*(x: Int): Int

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-int-4/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法*(x:Int)方法用于返回该值与 x 的乘积。

> **方法定义:** Byte *(x: Int): Int
> **返回类型:**它返回这个值和 x 的乘积。

示例#1:

```scala
// Scala program of Byte *(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Int) function 
        val result = (64.toByte).*(12:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
768
```

示例 2:

```scala
// Scala program of Byte *(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Int) function 
        val result = (17.toByte).*(128:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
2176
```