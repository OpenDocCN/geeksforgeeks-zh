# Scala 字符串 hashCode()方法示例

> 原文:[https://www . geesforgeks . org/Scala-string-hashcode-method-with-example/](https://www.geeksforgeeks.org/scala-string-hashcode-method-with-example/)

利用 **hashCode()** 方法找到所述字符串的哈希码。

> **方法定义:** int hashCode()
> **返回类型:**返回给定字符串的整数 hash 码。

**示例#1:**

```scala
// Scala program of int hashCode()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying hashCode method
        val result = "Nidhi".hashCode()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
75262122

```

**例 2:**

```scala
// Scala program of int hashCode()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying hashCode method
        val result = " ".hashCode()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
32

```