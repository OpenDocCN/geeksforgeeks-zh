# Scala 迭代器 max()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-max-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-max-method-with-example/)

**max()** 方法属于抽象迭代器类的具体值成员。它在类*中定义。它被用来寻找最大的元素。*

> **方法定义:**def max【B】T2:A】(隐含顺序:数学。订购[乙]):甲
> 
> 其中， *B* 是定义排序的类型，*序*是用于比较元素的排序。
> 
> **返回类型:**返回关于订单*订单*所述集合中最大的元素。

**示例#1:**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(22, 36, 66, 19, 21)

        // Applying max method
        val iter1 = iter.max

        // Displays output
        println(iter1)

    }
}
```

**Output:**

```scala
66

```

因此，返回集合中最大的元素。
**例 2:**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2.2, 3.6, 6.6, 9.9, 2.1)

        // Applying max method
        val iter1 = iter.max

        // Displays output
        println(iter1)

    }
}
```

**Output:**

```scala
9.9

```