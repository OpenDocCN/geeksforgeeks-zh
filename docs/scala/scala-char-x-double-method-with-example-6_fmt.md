## Scala Char ==(x: Double)方法，示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-6/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-6/)

使用 `==(x: Double)` 方法来查找所述字符值是否等于“x”。“x”的类型必须是 `Double`。

### 方法定义
> `def ==(x: Double): Boolean`
>
> **返回类型:** 如果所述字符值等于“x”，则返回 `true`，否则返回 `false`。

### 示例 1

```scala
// Scala program of ==(x: Double)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying ==(x: Double) method 
        val result = 'D'.==(68.98756)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```

### 示例 2

```scala
// Scala program of ==(x: Double)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying ==(x: Double) method
        val result = 'Z'.==(90.00000)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```