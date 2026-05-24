# Scala SortedMap `empty()`方法示例

> 原文: [https://www.geeksforgeeks.org/scala-sortedmap-empty-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-empty-method-with-example/)

利用`empty()`方法清空`SortedMap`。

> **方法定义:** `def empty: SortedMap[A, B]`
>
> **返回类型:** 返回空的`SortedMap`。

## 示例#1:

```scala
// Scala program of empty()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

// Applying empty method
        val result = m1.empty

// Displays output
        println(result)

}
}
```

**Output:**

```scala
Map()
```

## 示例#2:

```scala
// Scala program of empty()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating an empty SortedMap
        val m1 = SortedMap("gopal" -> 10)

// Applying empty method
        val result = m1.empty

// Displays output
        println(result)

}
}
```

**Output:**

```scala
Map()
```