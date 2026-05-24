# Scala Char `isUnicodeIdentifierStart()` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-isunicodeidentifierstart-method-with-example/](https://www.geeksforgeeks.org/scala-char-isunicodeidentifierstart-method-with-example/)

使用 `isUnicodeIdentifierStart()` 方法来查找所述字符是否允许作为 Unicode 标识符中的第一个字符。
当且仅当下列条件之一成立时，字符以 Unicode 标识符开头:

*   `isLetter(ch)` 返回 `true`。
*   `getType(ch)` 返回 `LETTER_NUMBER`。

## 方法定义

```scala
def isUnicodeIdentifierStart: Boolean
```

**返回类型:** 如果指定的字符可以作为 Unicode 标识符中的第一个字符，则返回 `true`，否则返回 `false`。

## 例: 1

```scala
// Scala program of isUnicodeIdentifierStart()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isUnicodeIdentifierStart() method
        val result = ('b').isUnicodeIdentifierStart

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
true
```

## 例: 2

```scala
// Scala program of isUnicodeIdentifierStart()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isUnicodeIdentifierStart() method
        val result = ('_').isUnicodeIdentifierStart

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
false
```