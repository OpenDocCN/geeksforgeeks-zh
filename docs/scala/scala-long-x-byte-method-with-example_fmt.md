# Scala Long `!=(x: Byte)` 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/scala-long-x-byte-method-with-example/](https://www.geeksforgeeks.org/scala-long-x-byte-method-with-example/)

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `Long` 基本类型。`!=(x: Byte)` 方法用于检查给定的 `Long` 和 `Byte` 值是否不相等。

## 方法定义与返回值

**方法定义：**
```scala
def !=(x: Byte): Boolean
```

**返回值：**
如果该值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例

### 示例 1

```scala
// Scala program to explain working
// of Long !=(x: Byte) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Byte) function
        val result = (-128).toLong.!= (-2^7:Byte)

        // Displays output
        println(result)
    }
}
```

**输出：**
```scala
true
```

### 示例 2

```scala
// Scala program to explain working
// of Long !=(x: Byte) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Byte) function
        val result = 16.toLong.!= (2^4:Byte)

        // Displays output
        println(result)
    }
}
```

**输出：**
```scala
true
```