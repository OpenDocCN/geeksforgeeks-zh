# Scala List dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-list-dropright-method-with-example/)

利用 **dropRight()** 方法查找列表中除最后 n 个元素之外的所有元素。

> **方法定义:** def dropRight(n: Int):列表[A]
> 
> **返回类型:**返回列表中除最后 n 个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 1, 3, 3, 3, 5, 4, 5, 2)

        // Applying dropRight method
        val res = m1.dropRight(3)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 1, 3, 3, 3, 5)

```

**例 2:**

```scala
// Scala program of dropRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 1, 3, 3, 3, 5, 4, 5, 2)

        // Applying dropRight method
        val res = m1.dropRight(10)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List()

```