# Scala Char > =(x: Double)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-double-method-with-example-8/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-8/)

使用 **> =(x: Double)** 方法来查找所述字符值是否大于或等于‘x’。“x”的类型必须是 Double。

> **方法定义:** def > =(x: Double):布尔值
> 
> **返回类型:**如果所述字符值大于或等于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of >=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Double) method 
        val result = '\n'.>=(11.95666)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例:2#**

```scala
// Scala program of >=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Double) method
        val result = '\n'.>=(9.95666)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```