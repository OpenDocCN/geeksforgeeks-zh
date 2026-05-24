# Scala 字符串索引 Of(int ch，int fromIndex)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-index ofint-ch-int-from index-method-with-example/](https://www.geeksforgeeks.org/scala-string-indexofint-ch-int-fromindex-method-with-example/)

**indexOf(int ch，int fromIndex)** 方法与 indexOf()方法相同，但此方法从我们指定的索引开始查找字符。

> **方法定义:** int indexOf(int ch，int fromIndex)
> **返回类型:**返回参数中指定字符的索引。

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
        val result = "Nidhi".indexOf('i', 2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
4

```

所以，这里第一次出现“I”是在第二个索引是 4 之后，所以，4 作为输出返回。
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
        val result = "NidhiSingh".indexOf('h', 4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
9

```

这里，第四个索引后第一次出现的“h”是 9。所以，它回来了。