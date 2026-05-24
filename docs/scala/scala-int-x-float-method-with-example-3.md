# Scala Int %(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-float-method-with-example-3/](https://www.geeksforgeeks.org/scala-int-x-float-method-with-example-3/)

当指定的 int 值除以 Float 值时，使用 **%(x: Float)** 方法返回余数。

> **方法定义:** (Int_Value)。%(浮点值)
> 
> **返回类型:**当指定的 int 值除以 float 值时返回余数。

**示例#1:**

```scala
// Scala program of Int %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Float) function
        val result = (100).%(50.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

**例 2:**

```scala
// Scala program of Int %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Float) function
        val result = (100).%(40.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
20

```