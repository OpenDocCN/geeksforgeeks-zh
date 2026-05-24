# Scala 字符串 `startsWith` 方法（带示例）

> 原文：[https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-method-with-example/](https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-method-with-example/)

`startsWith` 方法用于检查所述字符串是否以我们指定的前缀开头。

## 方法定义
`Boolean startsWith(String prefix)`

## 返回类型
如果字符串以指定的前缀开头，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of startsWith()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying startsWith method
        val result = "GeeksforGeeks".startsWith("Geeks")

// Displays output
        println(result)

}
}
```

**输出：**

```scala
true
```

## 示例 2

```scala
// Scala program of startsWith()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying startsWith method
        val result = "GeeksforGeeks".startsWith("geeks")

// Displays output
        println(result)

}
}
```

**输出：**

```scala
false
```