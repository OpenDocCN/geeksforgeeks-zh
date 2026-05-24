# Scala String last indexof(int ch，int fromIndex)()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-last indexofint-ch-int-from index-method-with-example/](https://www.geeksforgeeks.org/scala-string-lastindexofint-ch-int-fromindex-method-with-example/)

**lastIndexOf()** 方法用于从我们为所述字符串指定的索引中返回我们在参数中指定的字符最后出现的索引。

> **方法定义:** int lastIndexOf(int ch，int fromIndex)
> **返回类型:**它从我们指定的索引中返回参数中字符最后一次出现的索引。

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
        val result = "GeeksforGeeks".lastIndexOf('e', 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2

```

这里，搜索从索引 4 开始，从右到左，并且首先出现的那个被返回。
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
        val result = "GeeksforGeeks".lastIndexOf('f', 1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1

```

这里，当从指定的索引从左向右搜索时，该方法不能找到所述字符。所以，它在这里返回-1。