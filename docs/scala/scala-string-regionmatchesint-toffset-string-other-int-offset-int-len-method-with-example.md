# Scala 字符串区域匹配(int toffset，String other，int offset，int len)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-regionmatchesent-toffset-string-other-int-offset-int-len-method-with-example/](https://www.geeksforgeeks.org/scala-string-regionmatchesint-toffset-string-other-int-offset-int-len-method-with-example/)

**regionMatches(int toffset，String other，int offset，int len)** 方法用于检查两个字符串区域是否相等。然而，这里*忽略*不包括在内。

> **方法定义:**布尔区域匹配(int toffset，String other，int offset，int len)
> **返回类型:**如果两个字符串区域匹配，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of int regionMatches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying regionMatches method
        val result = "Preeti".regionMatches(0, "Preeti", 0, 4)

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
// Scala program of int regionMatches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying regionMatches method
        val result = "Preeti".regionMatches(0, "pReeti", 0, 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```