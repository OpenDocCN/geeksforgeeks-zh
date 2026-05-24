# Scala List init()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-init-method-with-example/](https://www.geeksforgeeks.org/scala-list-init-method-with-example/)

使用 **init()** 方法查找列表中除最后一个元素之外的所有元素。

> **方法定义:**定义初始化:列表[A]
> 
> **返回类型:**返回列表中除最后一个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of init()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 21)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
List(3, 6, 2, 9)

```

**例 2:**

```scala
// Scala program of init()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
List()

```