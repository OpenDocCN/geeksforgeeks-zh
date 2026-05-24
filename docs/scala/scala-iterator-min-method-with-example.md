# Scala 迭代器 min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-min-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-min-method-with-example/)

min()方法属于抽象迭代器类的具体值成员。它在类 *IterableOnceOps* 中定义。它被用来寻找最小的元素。

> **方法定义:**def min【B】T2:A】(隐含顺序:数学。订购[乙]):甲
> 
> 其中， *B* 是定义排序的类型，*序*是用于比较元素的排序。
> 
> **返回类型:**返回集合中相对于订单*订单*的最小元素。

**示例#1:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(50, 60, 11, 90, 21)

        // Applying min method
        val iter1 = iter.min

        // Displays output
        println(iter1)

    }
}
```

**Output:**

```scala
11

```

这里，返回指定集合的最小元素。
**例 2:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2.1, 3.3, 1.1, 4.6)

        // Applying min method
        val iter1 = iter.min

        // Displays output
        println(iter1)

    }
}
```

**Output:**

```scala
1.1

```