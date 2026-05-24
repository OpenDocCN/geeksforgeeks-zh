# Scala 字符串子序列()方法示例

> 原文:[https://www . geesforgeks . org/Scala-string-subserial-method-with-example/](https://www.geeksforgeeks.org/scala-string-subsequence-method-with-example/)

利用**子序列()**方法从给定的字符串中找到子序列，该子序列以我们指定的索引开始和结束。

> **方法定义:**字符序列子序列(int beginIndex，int endIndex)
> 
> **返回类型:**返回结果子序列。

**例:1#**

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

**Output:**

```scala
for

```

**例:2#**

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

**Output:**

```scala
forGeeks

```