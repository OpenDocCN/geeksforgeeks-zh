# Scala Int > =(x: Short)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-short-method-with-example-12/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-12/)

如果指定的 int 值大于或等于 Short 值，则使用 **> =(x: Short)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。> =(Short_Value)
> **返回类型:**如果指定的 int 值大于或等于 Short 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int >=(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >=(x: Short) function
        val result = (66).>=(55)

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
// Scala program of Int >=(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >=(x: Short) function
        val result = (50).>=(60)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```