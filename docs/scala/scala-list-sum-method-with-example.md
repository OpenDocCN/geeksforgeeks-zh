# Scala List sum()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-sum-method-with-example/](https://www.geeksforgeeks.org/scala-list-sum-method-with-example/)

使用 **sum()** 方法添加所述列表的所有元素。

> **方法定义:** def sum(num:数学。数字[B]): B
> 
> **返回类型:**返回列表所有元素的总和。

**示例#1:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5, 7)

        // Applying sum method
        val result = m1.sum

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
22

```

**例 2:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 0)

        // Applying sum method
        val result = m1.sum

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
1

```