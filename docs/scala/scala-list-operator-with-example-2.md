# Scala List:::()运算符，示例

> 原文:[https://www . geesforgeks . org/Scala-list-operator-with-example-2/](https://www.geeksforgeeks.org/scala-list-operator-with-example-2/)

Scala 中的**::()**运算符用于将参数中的列表连接到另一个列表。

> **方法定义:** def::(前缀:列表[A]):列表[A]
> 
> **返回类型:**将一个列表加入另一个列表后返回一个列表。

**示例#1:**

```scala
// Scala program of :::()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating two lists
        val m1 = List(1, 2, 3)
        val m2 = List(4, 5, 6)

        // Applying ::: operator
        val res = m1.:::(m2)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(4, 5, 6, 1, 2, 3)

```

**例 2:**

```scala
// Scala program of :::()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating two lists
        val m1 = List(1, 2, 3)
        val m2 = List()

        // Applying ::: operator
        val res = m1.:::(m2)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 2, 3)

```