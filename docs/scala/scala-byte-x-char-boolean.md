# 位元组比例！=(x:char):boolean

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-byte-x-char-boolean/

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法！=(x:Char)方法用于在值不等于指定值 x 时返回 true，否则返回 false。

> **方法定义:**字节！=(x: Char):布尔值
> **返回类型:**如果值不等于指定值，则返回 true，否则返回 false。

示例#1:

```scala
// Scala program of Byte !=(x: Char) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte !=(x: Char) function 
        val result = (68.toByte).!=('D':Char) 

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
// Scala program of Byte !=(x: Char) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte !=(x: Char) function 
        val result = (100.toByte).!=('G':Char) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true
```