# Scala Int %(x: Int)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-int-method-with-example-4/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-4/)

当指定的第一个 int 值除以第二个 Int 值时，使用 **%(x: Int)** 方法返回余数。

> **方法定义:** (First_Int_Value)。%(秒 _ 整数 _ 值)
> 
> **返回类型:**当指定的第一个 int 值除以第二个 int 值时返回余数。

**示例#1:**

```scala
// Scala program of Int %(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Int) function
        val result = (100).%(50)

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
// Scala program of Int %(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Int) function
        val result = (100).%(40)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
20

```