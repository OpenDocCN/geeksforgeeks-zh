# 斯卡拉短！=(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-float-method-with-example-3/](https://www.geeksforgeeks.org/scala-short-x-float-method-with-example-3/)

**！=(x:浮点)**方法用于检查所述短值是否不等于“x”。“x”是浮点型的。

> **方法定义:** def！=(x:浮点):布尔值
> 
> **返回类型:**如果所述短值不等于‘x’，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) method 
        val result = (995).!=(44.5)

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
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) method
        val result = (66).!=(66.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```