# Scala 迭代器 filterNot()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-filter not-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-filternot-method-with-example/)

**filterNot()** 方法属于类*抽象迭代器*的具体值成员。它是在类*迭代器*和 *IterableOnceOps* 中定义的。它选择所述迭代器中不满足给定谓词的所有元素。

> **方法定义:**def filter not(p:(A)=>Boolean:迭代器[A]
> 
> **返回类型:**它返回一个新的迭代器，该迭代器包含所述迭代器中不满足给定谓词 p 的所有元素。

**示例#1:**

```scala
// Scala program of filterNot()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 9, 5, 1, 13)

        // Applying filterNot method
        val x = iter.filterNot(x => {x % 3 != 0})

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

**例 2:**

```scala
// Scala program of filterNot()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(2, 4, 5, 1, 13)

        // Applying filterNot method
        val x = iter.filterNot(x => {x % 2 == 0})

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
5

```