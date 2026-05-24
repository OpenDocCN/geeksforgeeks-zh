# Scala List::()运算符，示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-operator-with-example/](https://www.geeksforgeeks.org/scala-list-operator-with-example/)

Scala 中的**:()**运算符用于向列表的开头添加一个元素。

> **方法定义:** def ::(x: A):列表[A]
> 
> **返回类型:**在列表的开头添加一个元素后，返回指定的列表。

**示例#1:**

```scala
// Scala program of ::()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3)

        // Applying :: operator
        val res = m1.::("5")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(5, 1, 2, 3)

```

**例 2:**

```scala
// Scala program of ::()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3)

        // Applying :: operator
        val res = m1.::("1")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 1, 2, 3)

```