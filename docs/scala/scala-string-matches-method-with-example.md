# Scala 字符串匹配()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-matches-method-with-example/](https://www.geeksforgeeks.org/scala-string-matches-method-with-example/)

**matches()** 方法用于检查所述字符串是否与参数中指定的正则表达式匹配。

> **方法定义:**布尔匹配(字符串正则表达式)
> **返回类型:**如果字符串匹配正则表达式，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of int matches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying matches method
        val result = "Preeti".matches(".*i")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

因此，这里正则表达式与所述字符串匹配。所以，它返回真。
**例 2:**

```scala
// Scala program of int matches()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying matches method
        val result = "Preeti".matches(".i.*")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```