# Scala 字符串开始用(字符串前缀)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-starts with string-prefix-method-with-example/](https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-method-with-example/)

**startsWith(字符串前缀)**方法用于检查所述字符串是否以我们指定的前缀开头。

> **方法定义:**布尔开始带(字符串前缀)
> 
> **返回类型:**如果字符串以指定的前缀开头，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of startsWith()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying startsWith method
        val result = "GeeksforGeeks".startsWith("Geeks")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例:2#**

```scala
// Scala program of startsWith()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying startsWith method
        val result = "GeeksforGeeks".startsWith("geeks")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```