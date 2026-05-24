# Scala 迭代器 take() 方法详解

> 原文：[https://www.geeksforgeeks.org/scala-iterator-take-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-take-method-with-example/)

`take()` 方法属于抽象迭代器类的具体值成员。它用于选择所述迭代器的前 *n* 个元素。

> **方法定义：** `def take(n: Int): Iterator[A]`
>
> 其中，*n* 是从给定迭代器中获取的元素数。
>
> **返回类型：** 它从指定的迭代器或整个迭代器中返回前 *n* 个值，以较短的为准。

## 示例 #1

```scala
// Scala program of take()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a Iterator 
        val iter = Iterator(2, 3, 5, 7, 8, 9)

// Applying take method 
        val iter1 = iter.take(4)

// Applying while loop and
        // hasNext() method
        while(iter1.hasNext)
        {

// Applying next() method and
            // displaying output
            println(iter1.next())
        }
    }
}
```

**输出：**

```scala

```

这里，显示前四个元素，因为我们已经在方法中选择了前四个元素。

## 示例 #2

```scala
// Scala program of take()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a Iterator 
        val iter = Iterator(2, 3, 5, 7, 8, 9)

// Applying take method 
        val iter1 = iter.take(7)

// Applying while loop and
        // hasNext() method
        while(iter1.hasNext)
        {

// Applying next() method and
            // displaying output
            println(iter1.next())
        }
    }
}
```

**输出：**

```scala

```

这里，整个迭代器显示为其中的元素数量比方法选择的元素数量少。因此，显示较短的一个。