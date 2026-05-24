# Scala 字符串子串(int beginIndex，int endIndex)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-substring int-beginindex-int-endindex-method-with-example/](https://www.geeksforgeeks.org/scala-string-substringint-beginindex-int-endindex-method-with-example/)

**子串(int beginIndex，int endIndex)** 方法用于从以指定索引开始和结束的所述字符串中找到子串。

> **方法定义:**字符串子串(int beginIndex，int endIndex)
> 
> **返回类型:**它返回字符串，该字符串是所述字符串的一部分。

**注:**与子序列法相同，但两者唯一的区别是子序列返回 *CharSequence* 但上述方法返回字符串。

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
        val result = "GeeksforGeeks".substring(4, 8)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
sfor

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
        val result = "GeeksforGeeks".substring(0, 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Geek

```