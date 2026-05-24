# Scala String lastIndexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-last indexof-method-with-example/](https://www.geeksforgeeks.org/scala-string-lastindexof-method-with-example/)

**lastIndexOf()** 方法用于从所述字符串中返回我们在参数中指定的字符的最后出现的索引。

> **方法定义:**int last indexof(int ch)
> **返回类型:**返回参数中字符最后一次出现的索引。

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
        val result = "GeeksforGeeks".lastIndexOf('G')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
8

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
        val result = "GeeksforGeeks".lastIndexOf('e')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10

```