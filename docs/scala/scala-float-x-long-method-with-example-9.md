# 斯卡拉飘！=(x:长)法举例

> 原文:[https://www . geesforgeks . org/Scala-float-x-long-method-with-example-9/](https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-9/)

**！=(x: Long)** 方法用于检查给定的 Float 和 Long 值是否相等。

> **方法定义:** (Float_Value)！=(x:长)
> 
> **返回类型:**如果给定的 Float 和 Long 值不相等，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float !=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Long) function
        val result = (12.4).!=(12.4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float !=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Long) function
        val result = (12.4).!=(126)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```