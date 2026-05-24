# Scala Float isValidChar()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-float-isvalidchar-method-with-example/](https://www.geeksforgeeks.org/scala-float-isvalidchar-method-with-example/)

如果指定的数字为零或在 Scala 的 `Char.MinValue` 和 `Char.MaxValue` 范围内，则使用 `isValidChar()` 方法返回 `true`，否则返回 `false`。

## 方法定义

`(Float_Number).isValidChar`

## 返回类型

如果指定的数字为零或在 `Char.MinValue` 和 `Char.MaxValue` 范围内，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of Float isValidChar()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isValidChar method
        val result = (0).isValidChar

// Displays output
        println(result)

}
}
```

**Output:**

```scala
true
```

## 示例 2

```scala
// Scala program of Float isValidChar()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isValidChar method
        val result = (5.9).isValidChar

// Displays output
        println(result)

}
}
```

**Output:**

```scala
false
```