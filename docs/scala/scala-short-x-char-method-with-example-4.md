# 斯卡拉短！=(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-char-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-char-method-with-example-4/)

**！=(x: Char)** 方法用于检查所述短值是否不等于“x”。“x”是 Char 类型。

> **方法定义:** def！=(x: Char):布尔值
> 
> **返回类型:**如果所述短值不等于‘x’，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of !=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) method 
        val result = (1000).!=('C')

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
// Scala program of !=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) method
        val result = (666).!=('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```