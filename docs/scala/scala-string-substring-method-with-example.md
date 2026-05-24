# Scala String substring()方法示例

> 原文:[https://www . geesforgeks . org/Scala-string-substring-method-with-example/](https://www.geeksforgeeks.org/scala-string-substring-method-with-example/)

**子串()**方法用于从指定的索引开始的所述串中找到子串。

> **方法定义:**字符串子串(int beginIndex)
> 
> **返回类型:**它返回从我们指定的索引开始的给定字符串的内容。

**例:1#**

```scala
// Scala program of substring()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying substring method
        val result = "GeeksforGeeks".substring(8)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Geeks

```

**例:2#**

```scala
// Scala program of substring()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying substring method
        val result = "GeeksforGeeks".substring(11)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
ks

```