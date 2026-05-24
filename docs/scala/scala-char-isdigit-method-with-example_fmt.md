# Scala Char isDigit() 方法示例

> 原文: `https://www.geeksforgeeks.org/scala-char-isdigit-method-with-example/`

`isDigit()` 方法用于检查所述字符是否为数字。

**方法定义:** 定义为 `def isDigit: Boolean`

**返回类型:** 如果所述字符为数字，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of isDigit()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isDigit method
        val result = '9'.isDigit

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
// Scala program of isDigit()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isDigit method
        val result = 'g'.isDigit

// Displays output
        println(result)

}
}
```

**输出:**

```scala
false
```