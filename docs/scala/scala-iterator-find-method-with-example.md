# Scala 迭代器 find()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-find-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-find-method-with-example/)

**find()** 方法属于类*抽象迭代器*的具体值成员。它在类*中定义。它找到满足给定谓词的所述集合的第一个元素。对于无限大小的集合，它不会终止。*

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**它返回一个包含所述集合的第一个元素的选项值，该元素满足所使用的谓词，否则如果不存在，则返回*无*。

**示例#1:**

```scala
// Scala program of find()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(2, 4, 5, 1, 13)

        // Applying find method
        val result= iter.find(x => {x % 2 == 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Some(2)

```

**例 2:**

```scala
// Scala program of find()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 12, 21)

        // Applying find method
        val result= iter.find(x => {x % 3 != 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
None

```