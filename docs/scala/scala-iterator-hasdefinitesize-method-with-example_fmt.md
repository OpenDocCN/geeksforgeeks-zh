# Scala 迭代器的 `hasDefiniteSize()` 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-iterator-hasdefinitesize-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-hasdefinitesize-method-with-example/)

`hasDefiniteSize()` 方法是 `Traversable` 类的具体成员。它检查所述可遍历集合是否具有有限的大小。

**方法定义：**

```scala
def hasDefiniteSize: Boolean
```

**返回类型：**
如果指定的集合大小有限，则返回 `true`，否则返回 `false`。如果迭代器为空，则返回 `true`，否则返回 `false`。

**示例：**

```scala
// Scala program of hasDefiniteSize()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Declaring an empty iterator
        val iter = Iterator()

// Applying hasDefiniteSize method
        val result = iter.hasDefiniteSize

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
true
```

这里，迭代器是空的，所以方法返回 `true`。

**示例：**

```scala
// Scala program of hasDefiniteSize()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Declaring an iterator
        val iter = Iterator(2, 3, 4, 9, 6)

// Applying hasDefiniteSize method
        val result = iter.hasDefiniteSize

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
false
```

这里，所述迭代器是非空的，因此方法返回 `false`。