# Scala Int！=(x:短)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-short-method-with-example-5/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-5/)

**！=(x: Short)** 如果 int 值不等于指定的 Short 值，则使用方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。！=(短值)
> 
> **返回类型:**如果 int 值不等于指定的 short 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int !=(x: short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: short) function
        val result = (100).!=(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of Int !=(x: short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: short) function
        val result = (100).!=(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```