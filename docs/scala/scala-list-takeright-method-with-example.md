# Scala List takeRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-list-takeright-method-with-example/)

使用 **takeRight()** 方法选择列表的最后 n 个元素。

> **方法定义:**def taker right(n:Int):List[A]
> 
> **返回类型:**返回列表最后的‘n’个元素。

**示例#1:**

```scala
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5, 7)

        // Applying takeRight method
        val result = m1.takeRight(3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(4, 5, 7)

```

**例 2:**

```scala
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5, 7)

        // Applying takeRight method
        val result = m1.takeRight(7)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(1, 2, 3, 4, 5, 7)

```