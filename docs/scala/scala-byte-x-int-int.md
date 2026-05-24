# 位元组比例(x: Int): Int

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-int/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法% x:Int 方法用于返回该值除以 x 的余数

> **方法定义:** Byte %(x: Int): Int
> **返回类型:**返回该值除以 x 的余数。

示例#1:

```scala
// Scala program of Byte %(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Int) function 
        val result = (100.toByte).%(3:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
1
```

示例 2:

```scala
// Scala program of Byte %(x: Int)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Int) function 
        val result = (167.toByte).%(3:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2
```