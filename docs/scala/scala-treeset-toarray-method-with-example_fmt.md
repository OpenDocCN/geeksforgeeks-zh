# Scala TreeSet toArray()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-treeset-toarray-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-toarray-method-with-example/)

`toArray()` 用于返回由树集合的所有元素组成的数组。

> **方法定义:** 定义为 `def toArray: Array[A]`
>
> **返回类型:** 它返回一个由 `TreeSet` 的所有元素组成的数组。

## 示例 1

```scala
// Scala program of toArray()
// method

// Import TreeSet
import scala.collection.mutable._

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating TreeSet
        val t1 = TreeSet(3, 1, 5, 2, 4)

// Print the TreeSet
        println(t1)

// Applying toArray method
        val result = t1.toArray

// Display output
        print("Elements in the array: ")

for(elem <- result)
            print(elem + " ")

}
}
```

**输出:**

```scala
TreeSet(1, 2, 3, 4, 5)
Elements in the array: 1 2 3 4 5
```

## 示例 2

```scala
// Scala program of toArray()
// method

// Import TreeSet
import scala.collection.mutable._

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating TreeSet
        val t1 = TreeSet("u", "a", "i", "o", "e")

// Print the TreeSet
        println(t1)

// Applying toArray method
        val result = t1.toArray

// Display output
        print("Elements in the array: ")

for(elem <- result)
            print(elem + " ")

}
}
```

**输出:**

```scala
TreeSet(a, e, i, o, u)
Elements in the array: a e i o u
```