# Scala 字符串 startsWith(String prefix, int toffset) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-int-toffset-method-with-example/](https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-int-toffset-method-with-example/)

`startsWith(String prefix, int toffset)` 方法用于检查所述字符串是否在指定索引处以给定的前缀开始。

> **方法定义:** `Boolean startsWith(String prefix, int toffset)`
>
> **返回类型:** 如果字符串在指定的索引处以指定的前缀开头，则返回 `true`，否则返回 `false`。

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
        val result = "GeeksforGeeks".startsWith("eks", 2)

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
// Scala program of startsWith()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying startsWith method
        val result = "GeeksforGeeks".startsWith("Eks", 2)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
false
```