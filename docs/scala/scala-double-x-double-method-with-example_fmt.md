# Scala Double !=(x: Double) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-double-x-double-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-double-method-with-example/)

在 Scala 中，`Double` 是一个 64 位的浮点数，相当于 Java 的 `Double` 原语类型。`!=(x: Double)` 方法用于检查给定的 `Double` 值是否相等。

## 方法定义

`def !=(x: Double): Boolean`

## 返回值

如果该值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program to explain working 
// of Double !=(x: Double) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Double) function
        val result = (10.1234500).toLong.!=(10:Double)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```

## 示例 #2

```scala
// Scala program to explain working
// of Long !=(x: Double) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Double) function
        val result = 11.86000000.toLong.!= (1296000:Double)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
true
```