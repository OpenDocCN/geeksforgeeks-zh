# Scala 字符串索引 Of(字符串，int fromIndex)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-indexofstring-str-int-from index-method-with-example/](https://www.geeksforgeeks.org/scala-string-indexofstring-str-int-fromindex-method-with-example/)

**indexOf(String str，int fromIndex)** 方法用于返回子字符串的索引，该索引首先出现在我们在所述字符串中指定的索引中。

> **方法定义:** int indexOf(String str，int fromIndex)
> **返回类型:**它从参数中指定的索引返回子字符串的索引。

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
        val result = "Nidhisinghis".indexOf("his", 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
9

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
        val result = "Nidhisinghis".indexOf("is", 5)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10

```