# Scala Int > (x: Long)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-long-method-with-example-11/](https://www.geeksforgeeks.org/scala-int-x-long-method-with-example-11/)

如果指定的 int 值大于 Long 值，则使用 **> (x: Long)** 方法返回 true。

> **方法定义:** (Int_Value)。> (Long_Value)
> **返回类型:**如果指定的 int 值大于 Long 值，则返回 true。

**示例#1:**

```scala
// Scala program of Int >(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Long) function
        val result = (65).>(10)

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
// Scala program of Int >(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Long) function
        val result = (50).>(100)

        // Displays output
        println(result)

    }
}  
```

**Output:**

```scala
false

```