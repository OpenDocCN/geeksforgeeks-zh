# Scala Char toLower()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-to lower-method-with-example/](https://www.geeksforgeeks.org/scala-char-tolower-method-with-example/)

使用 **toLower()** 方法找到所述字符值的小写字母。

> **方法定义:**定义为低:字符
> 
> **返回类型:**返回 Char。

**例:1#**

```scala
// Scala program of toLower()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Applying toLower() method 
        val result = 'A'.toLower

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
a

```

**例:2#**

```scala
// Scala program of toLower()
// method
// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Applying toLower() method
        val result = 'Z'.toLower

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
z

```