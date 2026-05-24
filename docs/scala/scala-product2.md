# Scala | Product2

> 原文:[https://www.geeksforgeeks.org/scala-product2/](https://www.geeksforgeeks.org/scala-product2/)

**Product2** 是 Scala 中的一个[特性，是两个元素的笛卡尔乘积。在内置类中，它可以被认为是两个元素的元组。这里的线性超类型是*产品*、*等于*、*任意*，这里的子类是*tuple 2*。产品 2 扩展了如下产品:](https://www.geeksforgeeks.org/scala-traits/)

```scala
Product2[+T1, +T2] extends Product
```

这里，T1 和 T2 是元素的类型。
现在，我们来看一些例子。
**例:**

```scala
// Scala program of a trait
// Product2

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String]) 
    {

        // Applying Produt2 trait and
        // assigning values
        val pro: Product2[String, Int] = ("Nidhi", 24)

        // Displays the first element
        println(pro._1)

        // Displays the second element
        println(pro._2)

    }
}
```

**Output:**

```scala
Nidhi
24

```

这里， **_1** 是上述产品第一要素的延伸， **_2** 是产品第二要素的延伸。

**示例:**

```scala
// Scala program of a map
// using trait Product2

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying Product2 trait with
        // an iterator
        val x : Iterator[Product2[String, Int]] =

        // List of the elements 
        List("Nidhi" -> 24, "Nisha" -> 22, "Preeti" -> 26).iterator

        // Calling first types of elements 
        // of the trait Product2 from the
        // List using map method
        val result = x.map(y => y._1).toList

        // Displays String types of
        // the list
        println(result)

    }
}
```

**Output:**

```scala
List(Nidhi, Nisha, Preeti)

```

因此，迭代在这里很容易完成。