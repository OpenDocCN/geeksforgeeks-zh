# Scala 字符串 indexOf()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-indexof-method-with-example/](https://www.geeksforgeeks.org/scala-string-indexof-method-with-example/)

**indexOf()** 方法用于查找字符串中字符第一次出现的索引，并且该字符作为参数出现在该方法中。

> **方法定义:** int indexOf(int ch)
> **返回类型:**返回参数中所述字符的索引。

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
        val result = "Nidhi".indexOf('i')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```

所以，这里第一次出现“I”是在索引一，所以，1 作为输出返回。
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
        val result = "Nidhi".indexOf('h')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3

```