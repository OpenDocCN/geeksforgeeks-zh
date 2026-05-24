# Scala 字符串开始用(字符串前缀，int toffset)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-startswithstring-prefix-int-toffset-method-with-example/](https://www.geeksforgeeks.org/scala-string-startswithstring-prefix-int-toffset-method-with-example/)

**start with(字符串前缀，int toffset)** 方法用于检查所述字符串是否以前缀开始，该前缀是否由我们在指定索引处指定。

> **方法定义:**布尔开始(字符串前缀，int toffset)
> 
> **返回类型:**如果字符串在指定的索引处以指定的前缀开头，则返回真，否则返回假。

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
        val result = "GeeksforGeeks".startsWith("eks", 2)

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
        val result = "GeeksforGeeks".startsWith("Eks", 2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```