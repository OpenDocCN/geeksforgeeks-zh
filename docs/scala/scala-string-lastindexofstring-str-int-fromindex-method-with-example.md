# Scala String last indexof(String String，int fromIndex)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-last indexofstring-str-int-from index-method-with-example/](https://www.geeksforgeeks.org/scala-string-lastindexofstring-str-int-fromindex-method-with-example/)

**lastIndexOf(String str，int fromIndex)** 方法用于从所述字符串的从右到左指定的索引中返回我们在参数中指定的子字符串的最后出现的索引。

> **方法定义:** int lastIndexOf(String str，int fromIndex)
> **返回类型:**从指定的索引返回参数中指定的子字符串最后一次出现的索引。

**示例#1:**

```scala
// Scala program of int lastIndexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying lastIndexOf method
        val result = "GeeksforGeeks".lastIndexOf("ek", 12)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10

```

**例 2:**

```scala
// Scala program of int lastIndexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying lastIndexOf method
        val result = "GeeksforGeeks".lastIndexOf("Geek", 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```