# Scala 序列

> 原文:[https://www.geeksforgeeks.org/scala-sequence/](https://www.geeksforgeeks.org/scala-sequence/)

**序列**是`iterable`类的可迭代集合。它用于表示具有定义的元素顺序(即保证不可变)的索引序列。序列的元素可以使用它们的索引来访问。方法`apply`用于索引的目的。序列也可以使用方法`reverse`和`reverseIterator`可逆地访问。
指数范围从 0 到(n–1)其中，n=序列长度。为了找到子序列，序列支持各种方法。方法如`indexOf`、`segmentLength`、`prefixLength`、`lastIndexWhere`、`lastIndexOf`、`startsWith`、`endsWith`。序列有两个主要子序列，即**索引序列**和**线性序列**，它们提供不同的性能保证。`IndexedSeq`提供对元素的快速随机访问，而`LinearSeq`仅通过`head`提供对第一个元素的快速访问，并且还包含一个快速尾部操作。

### 示例#1

```scala
// Scala program to illustrate sequence
import scala.collection.immutable._

object GFG
{
    // Main Method
    def main(args:Array[String])
    {
        // Initializing sequence
        var seq:Seq[Int] = Seq(1,2,3,4,5,6)

        // Printing Sequence
        seq.foreach((element:Int) => print(element+","))
        println("\nElements Access Using Index")
        println(seq(0))
        println(seq(1))
        println(seq(2))
        println(seq(3))
        println(seq(4))
        println(seq(5))
    }
}
```

**Output:**

```scala
1,2,3,4,5,6,
Elements Access Using Index
1
2
3
4
5
6
```

## 序列中使用的一些预定义方法

*   `def apply(index: Int): A` -> 从序列中选择一个元素
*   `def contains[A1 >: A](elem: A1): Boolean` -> 检查序列是否包含给定的元素
*   `def count(p: (A) => Boolean): Int` -> 计算满足谓词的元素数量
*   `def length: Int` -> 给出序列的长度
*   `def copyToArray(xs: Array[A], start: Int, len: Int): Unit` -> 用于将序列的元素复制到数组中
*   `def endsWith[B](that: GenSeq[B]): Boolean` -> 检查序列是否以给定的序列结束
*   `def head: A` -> 它选择序列的第一个元素。
*   `def indexOf(elem: A): Int` -> 查找序列中第一次出现的值的索引
*   `def isEmpty: Boolean` -> 测试序列的空性。
*   `def lastIndexOf(elem: A): Int` -> 查找序列中某个值最后一次出现的索引
*   `def reverse: Seq[A]` -> 以逆序返回包含元素的新序列。

### 示例#2

```scala
// Scala program to illustrate sequence
object MainObject
{
    // Main Method
    def main(args:Array[String])
    {
        // Initializing sequence
        var seq:Seq[Int] = Seq(1, 2, 3, 4, 5, 6)

        // Printing Sequence
        seq.foreach((element:Int) => print(element+","))

        // Using Some Predefined Methods
        println("\nis Empty: "+ seq.isEmpty)
        println("\nEnds with (5,6): "+ seq.endsWith(Seq(5,6)))
        println("\nLength of sequence: "+ seq.length)
        println("\ncontains 3: "+ seq.contains(3))
        println("\nlast index of 4 : "+ seq.lastIndexOf(4))
        println("\nReversed sequence: "+ seq.reverse)
    }
}
```

**Output:**

```scala
1,2,3,4,5,6,
is Empty: false
Ends with (5,6): true
Length of sequence: 6
contains 3: true
last index of 4 : 3
Reversed sequence: List(6, 5, 4, 3, 2, 1)
```