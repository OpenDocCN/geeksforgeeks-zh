# 斯卡拉短！=(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-int-method-with-example-3/](https://www.geeksforgeeks.org/scala-short-x-int-method-with-example-3/)

**！=(x: Int)** 方法用于检查所述短值是否不等于“x”。而“x”是 Int 类型的。

> **方法定义:** def！=(x: Int):布尔值
> 
> **返回类型:**如果所述短值不等于‘x’，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of !=(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Int) method 
        val result = (1000).!=(34)

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
// Scala program of !=(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Int) method
        val result = (666).!=(666)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```