# Scala ListSet min()方法示例

> 原文：`https://www.geeksforgeeks.org/scala-listset-min-method-with-example/`

在 Scala `ListSet` 中，利用 `min()` 方法寻找所述列表中所有元素的最小元素。

> 方法定义：`def min[B >: A](implicit ord: math.Ordering[B]): A`
>
> 返回类型：它返回指定 `ListSet` 集中所有元素中最小的元素。

## 例 1

```scala
// Scala program of min()
// method
import scala.collection.immutable._
// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = ListSet(1, 2, 3)

        // Applying min method
        val result = m1.min

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala

```

## 例 2

```scala
// Scala program of min()
// method
import scala.collection.immutable._
// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = ListSet(1, 2, -3)

        // Applying min method
        val result = m1.min

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala

```