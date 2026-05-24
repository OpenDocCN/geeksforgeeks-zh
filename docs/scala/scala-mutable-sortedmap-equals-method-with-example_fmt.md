# Scala 可变 SortedMap equals()方法，示例

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedmap-equals-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-equals-method-with-example/)

`equals()`方法用于检查两个排序的映射是否具有相同的键值对。

> **方法定义:** `def equals(that: Any): Boolean`
>
> **返回类型:** 如果两个排序映射的键值对相同，则返回`true`，否则返回`false`。

## 示例 1

```scala
// Scala program of equals()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Creating SortedMaps
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = SortedMap("cs" -> 2, "for" -> 3, "geeks"-> 5)

// Applying equals method
        val result = m1.equals(m2)

// Displays output
        println(result)

    }
}
```

**Output:**

```scala
true
```

## 示例 2

```scala
// Scala program of equals()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Creating SortedMaps
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = SortedMap("cs" -> 2, "fo" -> 2, "geeks"-> 5)

// Applying equals method
        val result = m1.equals(m2)

// Displays output
        println(result)

    }
}
```

**Output:**

```scala
false
```