# Scala Int！=(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-float-method-with-example-4/](https://www.geeksforgeeks.org/scala-int-x-float-method-with-example-4/)

**！=(x: Float)** 如果 int 值不等于指定的 Float 值，则使用方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。！=(Float_Value)
> **返回类型:**如果 int 值不等于指定的 Float 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: Float) function
        val result = (100).!=(50.0)

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
// Scala program of Int !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: Float) function
        val result = (100).!=(100.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```