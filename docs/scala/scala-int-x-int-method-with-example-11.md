# Scala Int > (x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-int-method-with-example-11/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-11/)

如果指定的第一个 int 值大于第二个 Int 值，则使用 **> (x: Int)** 方法返回 true。

> **方法定义:** (First_Int_Value)。> (Second_int_Value)
> **返回类型:**如果指定的第一个 Int 值大于第二个 Int 值，则返回 true。

**示例#1:**

```scala
// Scala program of Int >(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Int) function
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
// Scala program of Int >(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Int) function
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