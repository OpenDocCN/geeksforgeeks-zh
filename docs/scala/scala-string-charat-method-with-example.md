# Scala 字符串 charAt()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-charat-method-with-example/](https://www.geeksforgeeks.org/scala-string-charat-method-with-example/)

**charAt()** 方法用于返回参数中传递的索引的字符。

> **方法定义:** char charAt(int index)
> **返回类型:**返回参数中给定索引的 char。

**示例#1:**

```scala
// Scala program of charAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying charAt() method
        val result = m1.charAt(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
d

```

**例 2:**

```scala
// Scala program of charAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying charAt() method
        val result = m1.charAt(0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
N

```