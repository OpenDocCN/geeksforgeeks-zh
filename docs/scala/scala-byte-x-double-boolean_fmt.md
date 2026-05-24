# Scala Byte !=(x: Double): Boolean 方法详解

> 原文: `https://www.geeksforgeeks.org/scala-byte-x-double-boolean/`

在 Scala 中，`Byte` 是一个 8 位有符号整数（相当于 Java 的 `byte` 基元类型）。方法 `!=(x:Double)` 用于在值不等于指定值 `x` 时返回 `true`，否则返回 `false`。

> 方法定义: `Byte !=(x: Double): Boolean`
> 返回类型: 如果值不等于指定值，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of Byte !=(x: Double) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying Byte !=(x: Double) function 
        val result = (100.toByte).!=(50)

// Displays output 
        println(result)

} 
} 
```

**输出:**

```scala
true
```

## 示例 2

```scala
// Scala program of Byte !=(x: Double) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying Byte !=(x: Double) function 
        val result = (100.toByte).!=(100)

// Displays output 
        println(result)

} 
} 
```

**输出:**

```scala
false
```