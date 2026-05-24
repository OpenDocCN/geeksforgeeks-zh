# Scala Int ==(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-int-method-with-example-6/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-6/)

如果指定的第一个 int 值等于第二个 Int 值，则使用 **==(x: Int)** 方法返回真，否则返回假。

> **方法定义:** (First_Int_Value)。= =(Second _ int _ Value)
> 
> **返回类型:**如果指定的第一个 Int 值等于第二个 Int 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int ==(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ==(x: Int) function
        val result = (10).==(10)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true

```

**例 2:**

```scala
// Scala program of Int ==(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ==(x: Int) function
        val result = (500).==(100)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
false

```