# 斯卡拉短！=(x:短)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-short-method-with-example-5/](https://www.geeksforgeeks.org/scala-short-x-short-method-with-example-5/)

**！=(x:短)**方法用于检查所述短值是否不等于“x”。而‘x’是 Short 类型。

> **方法定义:** def！=(x:短):布尔值
> 
> **返回类型:**如果所述短值不等于‘x’，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of !=(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Short) method 
        val result = (999).!=(1000)

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
// Scala program of !=(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Short) method
        val result = (1000).!=(1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```