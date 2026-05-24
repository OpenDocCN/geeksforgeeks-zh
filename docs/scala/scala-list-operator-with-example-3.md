# Scala List +()运算符，示例

> 原文:[https://www . geesforgeks . org/Scala-list-operator-with-example-3/](https://www.geeksforgeeks.org/scala-list-operator-with-example-3/)

Scala 中的 **+()** 运算符用于向列表中添加一个元素。

> **方法定义:** def +(elem: A):列表[A]
> 
> **返回类型:**将所述元素添加到另一个元素后，返回该元素的列表。

**示例#1:**

```scala
// Scala program of +()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3)

        // Applying + operator
        val res = m1.+("10")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 2, 3)10

```

**例 2:**

```scala
// Scala program of +()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List()

        // Applying + operator
        val res = m1.+("10")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List()10

```