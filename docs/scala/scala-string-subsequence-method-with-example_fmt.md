# Scala 字符串 `subSequence()` 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-string-subsequence-method-with-example/](https://www.geeksforgeeks.org/scala-string-subsequence-method-with-example/)

利用 `subSequence()` 方法从给定的字符串中找到子序列，该子序列以我们指定的索引开始和结束。

## 方法定义

`CharSequence subSequence(int beginIndex, int endIndex)`

**返回类型：** 返回结果子序列。

## 示例 1

```scala
// Scala program of subSequence()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying subSequence method
        val result = "GeeksforGeeks".subSequence(5, 8)

// Displays output
        println(result)

}
}
```

**输出：**

```scala
for
```

## 示例 2

```scala
// Scala program of subSequence()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying subSequence method
        val result = "GeeksforGeeks".subSequence(5, 13)

// Displays output
        println(result)

}
}
```

**输出：**

```scala
forGeeks
```