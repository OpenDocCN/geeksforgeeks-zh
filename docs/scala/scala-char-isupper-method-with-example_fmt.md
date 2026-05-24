# Scala Char isUpper()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-isupper-method-with-example/](https://www.geeksforgeeks.org/scala-char-isupper-method-with-example/)

使用 `isUpper()` 方法检查所述字符值是否为大写。

## 方法定义
定义: `Boolean`

返回类型: 如果所述字符为大写，则返回 `true`，否则返回 `false`。

## 例:1

```scala
// Scala program of isUpper()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isUpper() method 
        val result = ('A').isUpper

// Displays output
        println(result)

}
} 
```

**Output:**

```scala
true
```

## 例:2

```scala
// Scala program of isUpper()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying isUpper() method
        val result = ('a').isUpper

// Displays output
        println(result)

}
} 
```

**Output:**

```scala
false
```