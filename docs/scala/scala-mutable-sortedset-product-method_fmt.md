# Scala 可变排序集 `product()` 方法

> 原文：[`https://www.geeksforgeeks.org/scala-mutable-sortedset-product-method/`](https://www.geeksforgeeks.org/scala-mutable-sortedset-product-method/)

在 Scala 可变集合中，利用 `SortedSet` 的 `product()` 方法来寻找 `SortedSet` 所有元素的乘积。

## 方法定义
```scala
def product: A
```

## 返回类型
返回排序集所有元素的乘积。

## 示例 #1
```scala
// Scala program of product()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(2, 3)

        // Applying product method
        val result = s1.product

        // Display output
        println(result)
    }
}
```

**Output:**
```scala

```

## 示例 #2
```scala
// Scala program of product()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(5, 4, 3, 2, 1)

        // Applying product method
        val result = s1.product

        // Display output
        println(result)
    }
}
```

**Output:**
```scala

```