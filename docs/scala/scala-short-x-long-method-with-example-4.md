# 斯卡拉短！=(x:长)法举例

> 原文:[https://www . geesforgeks . org/Scala-short-x-long-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-long-method-with-example-4/)

**！=(x:长)**方法用于检查所述短值是否不等于“x”。而 x 是龙型的。

> **方法定义:** def！=(x:长):布尔值
> 
> **返回类型:**如果所述短值不等于‘x’，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of !=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Long) method 
        val result = (1000).!=(100000L)

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
// Scala program of !=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Long) method
        val result = (999).!=(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```