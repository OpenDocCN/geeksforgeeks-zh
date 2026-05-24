# Scala Char ==(x: Char)方法示例

> 原文：[`https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-8/`](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-8/)

使用`==(x: Char)`方法来查找所述字符值是否等于`"x"`。`"x"`的类型必须是`Char`。

> **方法定义：** `def ==(x: Char): Boolean`
>
> **返回类型：** 如果所述字符值等于`"x"`，则返回`true`，否则返回`false`。

## 例：1

```scala
// Scala program of ==(x: Char)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying ==(x: Char) method
        val result = 'D'.==('D')

// Displays output
        println(result)

    }
}
```

**Output：**

```scala
true
```

## 例：2

```scala
// Scala program of ==(x: Char)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying ==(x: Char) method
        val result = 'D'.==('A')

// Displays output
        println(result)

    }
}
```

**Output：**

```scala
false
```