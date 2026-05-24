# Scala |聚合()函数

> 原文:[https://www.geeksforgeeks.org/scala-aggregate-function/](https://www.geeksforgeeks.org/scala-aggregate-function/)

**聚合()**功能用于组合结果。首先，应用*序列*操作，因为它是聚合()函数的第一个参数，然后是*组合*操作，该操作用于组合由所执行的序列操作生成的解。这个函数可以在 Scala 中的所有集合数据结构上实现，并且可以在 Scala 的可变和不可变集合数据结构上实现。它属于斯卡拉的 *TraversableOnce* 特性。
**语法:**

```scala
def aggregate[B](z: => B)(seqop: (B, A) => B, combop: (B, B) => B): B
```

哪里，

*   *B* 是聚合结果的类型， *z* 是聚合结果的初始值。
*   *seqop* 是序列运算的运算符，用于计算所述集合中每个元素的总和，并枚举集合中元素的总数。
*   *组合运算符*是一个组合运算符，用于组合通过集合的并行计算获得的结果。

*   **并行计算:**
    Let，List = (2，3，4，5，6，7，8)
    假设你有上述列表的三个线程，其中，让第一个线程为(2，3，4)，第二个线程为(5，6)，第三个线程为(7，8)。
    现在，让我们执行并行计算。
*   ```scala
    First thread = (2, 3, 4) = (2+3+4, 3) = (9, 3)
    // It is evaluated like below,
    // (sum of all the elements, total number of elements)

    ```

*   ```scala
    Second thread = (5, 6) = (5+6, 2) = (11, 2)

    ```

*   ```scala
    Third thread = (7, 8) = (7+8, 2) = (15, 2)

    ```

    最后，在并行计算之后，我们有(9，3)、(11，2)和(15，2)，现在这个*组合*操作符被用于组合每个线程的结果，即，

*   ```scala
    (9+11+15, 3+2+2) = (35, 7)
    ```

现在我们来看一个例子。
**例:**

```scala
// Scala program of aggregate()
// function

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String]) 
    {

        // Creating a list of numbers
        val s = List(1, 2, 3, 4)

        // Applying aggregate function
        val r = s.par.aggregate((0, 0))((s, r) =>(s._1 + r, s._2 + 1), 
                                (s,r) => (s._1 + r._1, s._2 + r._2))

        // Displays summation of all the 
        // elements in the list and also
        // total number of elements
        println("(Sum of all the elements , total number of elements) = "+r)
    }
}
```

**Output:**

```scala
(Sum of all the elements, total number of elements) = (10, 4)

```