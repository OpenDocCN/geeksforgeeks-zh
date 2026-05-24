# Scala 迭代器 dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-dropwhile-method-with-example/)

**dropWhile()** 方法属于类*抽象迭代器*的具体值成员。它是在类*迭代器*和 *IterableOnceOps* 中定义的。它删除满足所述谓词的元素的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:迭代器[A]
> 
> 其中， *p* 是要使用的谓词。
> 
> **返回类型:**返回所述迭代器的最长后缀，其第一个元素不满足所使用的谓词。

**示例#1:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(2, 3, 4, 6, 7)

        // Applying dropWhile method
        val x = iter.dropWhile(x => {x < 5})

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
6

```

**例 2:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7, 3, 4, 6, 7)

        // Applying dropWhile method
        val x = iter.dropWhile(x => {x % 2 != 0})

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
4

```