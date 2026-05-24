# Scala 迭代器 toSet()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-toset-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-toset-method-with-example/)

**toSet()** 方法属于抽象迭代器类的具体值成员。它是在类*中定义的。*

> **方法定义:**def to set【B】>:A:不可变。集合[B]
> 
> **返回类型:**从指定的集合中返回一个集合。

**示例#1:**

```scala
// Scala program of toSet()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator 
        val iter = Iterator(5, 6, 8, 9)

        // Applying toSet method 
        val result = iter.toSet

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set(5, 6, 8, 9)

```

**例 2:**

```scala
// Scala program of toSet()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an empty Iterator 
        val iter = Iterator()

        // Applying toSet method 
        val result = iter.toSet

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set()

```