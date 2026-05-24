# Scala 迭代器 drop()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-drop-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-drop-method-with-example/)

**drop()** 方法属于类*抽象迭代器*的具体值成员。它是在类*迭代器*和 *IterableOnceOps* 中定义的。它用于将迭代器 *n* 向前移动一个位置，如果 *n* 大于迭代器的长度，那么它将抛出一个异常。

> **方法定义:** def drop(n: Int):迭代器[A]
> 
> 其中， *n* 是要从指定迭代器中删除的元素数量。
> 
> **返回类型:**它返回所述迭代器的所有元素，除了第一个 *n 个*元素。

**示例#1:**

```scala
// Scala program of drop()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(4, 6, 10, 11, 13)

        // Applying drop method
        val x = iter.drop(4)

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
13

```

这里，前四个元素被删除，之后的所有元素都被返回。
**例 2:**

```scala
// Scala program of drop()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(2, 3, 4)

        // Applying drop method
        val x = iter.drop(1)

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```