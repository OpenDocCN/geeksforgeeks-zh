# Scala 字符串 lastIndexOf(字符串字符串)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-last indexofstring-str-method-with-example/](https://www.geeksforgeeks.org/scala-string-lastindexofstring-str-method-with-example/)

**lastIndexOf(String str)** 方法用于从所述字符串返回我们在参数中指定的子字符串的最后出现的索引。

> **方法定义:** int lastIndexOf(字符串)
> **返回类型:**返回参数中指定的子字符串最后一次出现的索引。

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
        val result = "GeeksforGeeks".lastIndexOf("ek")

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
        val result = "GeeksforGeeks".lastIndexOf("Geek")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
8

```