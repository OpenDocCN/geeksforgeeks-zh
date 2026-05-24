# Scala Char <=(x: Long)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-11/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-11/)

利用 `<= (x: Long)` 方法查找所述字符值是否小于或等于 `x`。而 `x` 的类型必须是 `Long`。

## 方法定义

> `def <=(x: Long): Boolean`
>
> **返回类型:** 如果所述字符值小于或等于 `x`，则返回 `true`，否则返回 `false`。

## 示例

### 例 1

```scala
// Scala program of <=(x: Long)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <=(x: Long) method
        val result = 'Z'.<=(100000L)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```

### 例 2

```scala
// Scala program of <=(x: Long)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <=(x: Long) method
        val result = 'Z'.<=(-100000L)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```