# Scala 字符串索引的(字符串字符串)方法示例

> 原文:[https://www . geesforgeks . org/Scala-string-indexofstring-str-method-with-example/](https://www.geeksforgeeks.org/scala-string-indexofstring-str-method-with-example/)

**indexOf(字符串)**方法用于返回所述字符串中最先出现的子字符串的索引。

> **方法定义:** indexOf(String str)
> **返回类型:**返回方法参数中指定的子字符串的索引。

**示例#1:**

```scala
// Scala program of int indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying indexOf method
        val result = "NidhiSingh".indexOf("dh")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2

```

**例 2:**

```scala
// Scala program of int indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying indexOf method
        val result = "NidhiSingh".indexOf("Sin")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5

```