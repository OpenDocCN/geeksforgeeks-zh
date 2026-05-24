# Scala 迭代器串联示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-concation-with-example/](https://www.geeksforgeeks.org/scala-iterator-concatenation-with-example/)

Scala 迭代器的*连接*是利用运算符 **++** 完成的。它属于类*抽象迭代器*的具体值成员。它被用来添加两个迭代器的元素。
在类*迭代器*中定义。

> **方法定义:** def ++(即:= >迭代器[A]):迭代器[A]
> 
> **返回类型:**它返回两个迭代器的串联。

**示例#1:**

```scala
// Scala program of concatenation
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ++ operator
        val result = Iterator(2,4).++(Iterator(6,7))

        // Applying while loop
        while(result.hasNext)
        {

        // Displays output
        println(result.next())

        }
    }
}
```

**Output:**

```scala
2
4
6
7

```

因此，迭代器的元素都被添加了，这里我们使用了 *hasNext* 和 *next* 方法，这些方法可以在 Scala 中的迭代器上调用。
**例 2:**

```scala
// Scala program of concatenation
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ++ operator
        val result = Iterator(0).++(Iterator(1))

        // Applying while loop
        while(result.hasNext)
        {

        // Displays output
        println(result.next())

        }
    }
}
```

**Output:**

```scala
0
1

```