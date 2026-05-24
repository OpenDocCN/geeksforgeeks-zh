# Scala Char to(end: Char)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-toend-char-method-with-example/](https://www.geeksforgeeks.org/scala-char-toend-char-method-with-example/)

`to(end: Char)` 方法用于返回从所述字符到 `end` 的范围，该范围在参数列表中给出，但在此 `step` 未在参数列表中指定。

## 方法定义
定义为 `to(end: Char): collection.immutable.Range`

## 返回类型
返回范围。

## 例:1#
```scala
// Scala program of to()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {
        // Applying to() method 
        val result = 'A'.to('G')

        // Displays output
        println(result)

    }
} 
```

**Output:**
```scala
NumericRange(A, B, C, D, E, F, G)
```

## 例:2#
```scala
// Scala program of to()
// method
// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {
        // Applying to() method
        val result = ('0').to('9')

        // Displays output
        println(result)

    }
} 
```

**Output:**
```scala
NumericRange(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
```