# Scala Int！=(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-int-method-with-example-5/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-5/)

**！=(x: int)** 方法用于在第一个 Int 值不等于指定的第二个 Int 值时返回 true，否则返回 false。

> **方法定义:** (First_Int_Value)。！=(Second_int_Value)
> **返回类型:**如果第一个 Int 值不等于指定的第二个 Int 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int !=(x: int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: int) function
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
// Scala program of Int !=(x: int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: int) function
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