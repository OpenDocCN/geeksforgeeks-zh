# Scala 字符串区域匹配()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-regionmatches-method-with-example/](https://www.geeksforgeeks.org/scala-string-regionmatches-method-with-example/)

**regionMatches()** 方法用于检查两个字符串区域是否相等。但是，如果参数列表中的*忽略*为真，则忽略大小写差异。

> **方法定义:**布尔区域匹配(布尔 ignoreCase，int toffset，String other，int offset，int len)
> **返回类型:**如果两个字符串区域匹配则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of regionMatches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying regionMatches method
        val result = "Preeti".regionMatches(false, 0, "Preeti", 0, 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of regionMatches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying regionMatches method
        val result = "Preeti".regionMatches(true, 0, "pReeti", 0, 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```