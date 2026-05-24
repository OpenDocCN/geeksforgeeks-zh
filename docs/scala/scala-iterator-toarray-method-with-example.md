# Scala 迭代器 toArray()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-to array-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-toarray-method-with-example/)

**toArray()** 方法属于抽象迭代器类的具体值成员。它用于将所述集合转换为数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**它从迭代器的元素中返回一个数组。

**示例#1:**

```scala
// Scala program of toArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator 
        val iter = Iterator(2, 3, 5, 7, 8, 9)

        // Applying toArray method 
        val result = iter.toArray

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
[I@506e1b77

```

**例 2:**

```scala
// Scala program of toArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator 
        val iter = Iterator(0, 1, 10)

        // Applying toArray method 
        val result = iter.toArray

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
[I@3535dee8

```