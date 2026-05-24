# 横向线刻度 | Set-2

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-traversal-set-2/

## 先决条件
- [标量特征可穿越|集合-1](https://www.geeksforgeeks.org/scala-trait-traversable-set-1/)

在前面的集合中，我们已经看到了类 `Taversable` 执行的一些操作。现在，在这一集里，我们将看到更多的操作。
这些操作如下:

### 转换操作
转换操作包括 `toList`, `toSeq`, `toArray`, `toStream`, `toSet`, `toMap`, `toIterable`, 和 `toIndexedSeq`。这些操作将 `Traversable` 集合转换为一个相对不同的东西。

**示例 :**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val q = Set(2, 7, 8, 15, 19)

// Converting Set to an Array
        val r = q.toArray

// Displaying an Array
        println(r)
    }
}
```

**输出:**

```
[I@506e1b77
```

这里，转换操作，即 `toArray` 将上述集合(或任何可遍历集合)转换成数组。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val q = Set(2, 6, 3, 7, 15, 20)

// Converting a Set to a List
        val r = q.toList

// Displaying a List
        println(r)

}
}
```

**输出:**

```
List(20, 6, 2, 7, 3, 15)
```

在这里，`toList` 将把任何可遍历的集合转换成列表。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating List of numbers 
        val x = List(9, 10, 13, 15, 18, 19)

// Converting a List to a Set
        val y = x.toSet

// Displaying a Set
        println(y)
    }
}
```

**输出:**

```
Set(10, 9, 13, 18, 19, 15)
```

这里，转换操作，即 `toSet` 将可遍历的任何集合转换成集合。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val m = Set(2, 4, 6, 8, 11, 15)

// Converting a Set to a Sequence
        val n = m.toSeq

// Displaying a Sequence
        println(n)
    }
}
```

**输出:**

```
ArrayBuffer(6, 2, 11, 8, 4, 15)
```

在这里，转换操作，即 `toSeq` 将任何可遍历集合转换成序列。这里生成的序列用于向量。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val x = Set(8, 10, 13, 15, 18)

// Converting a Set to an Iterable
        val y = x.toIterable

// Displaying an iterable
        println(y)
    }
}
```

**输出:**

```
Set(10, 13, 18, 8, 15)
```

这里，转换操作，即 `toIterable` (它迭代集合的所有元素)将把可遍历的任何集合转换成可迭代的。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val x = Set(2, 4, 5, 6, 7, 9)

// Convrerting a Set to an 
        // Indexed sequence 
        val y = x.toIndexedSeq

// Displaying an Indexed sequence
        println(y)
    }
}
```

**输出:**

```
Vector(5, 6, 9, 2, 7, 4)
```

这里，转换操作，即 `toIndexedSeq` 将任何可遍历转换成索引序列。这里生成的索引序列用于字符串和向量。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating Set of numbers 
        val x = Set(15, 17, 18, 19, 22, 25)

// Converting a Set to a stream 
        val y = x.toStream

// Displaying a Stream
        println(y)
    }
}
```

**输出:**

```
Stream(25, ?)
```

这里，转换操作，即 `toStream` 将可遍历的任何集合转换成流。该流被懒洋洋地枚举。

**示例:**

```scala
// Scala program of Conversion operation

// Creating object 
object Conversion
{

// Main method
    def main(args: Array[String]) 
    {

// Creating a Set of parameters 
        val x = Set("GfG" -> "CS portal", "Nidhi" -> "a Geek")
```

## Converting a Set to a Map

```scala
// Converting a Set to a Map
val y = x.toMap

// Displaying a Map
println(y)
```

**Output:**

```scala
Map(GfG -> CS portal, Nidhi -> a Geek)
```

在这里，`toMap`会将任何可遍历转换为地图。集合或列表必须有参数。

## Size info operations

Size info operations 包括 `nonEmpty`、`isEmpty`、`hasDefiniteSize` 和 `size`。这些操作可以指定给定的操作是有限的还是无限的。

**Example :**

```scala
// Scala program of Size info operation

// Creating object
object Sizeinfo
{

// Main method
    def main(args: Array[String])
    {

// Creating a map
        val x = Map("gfg" -> "cs", "nidhi" -> "geek")

// Applying Size info operation
        val y = x.isEmpty

// Displays true if map is
        // empty
        println(y)
    }
}
```

**Output:**

```scala
false
```

这里，`isEmpty`检查可遍历集合是否为空。如果元素集合为空，则打印 true；如果不为空，则打印 false。

**Example :**

```scala
// Scala program of Size info operation

// Creating object
object Sizeinfo
{

// Main method
    def main(args: Array[String])
    {

// Creating a map
        val x = Map("gfg" -> "cs", "nidhi" -> "geek")

// Applying Size info operation
        val y = x.nonEmpty

// Displays true if map is
        // not empty
        println(y)
    }
}
```

**Output:**

```scala
true
```

这里，`nonEmpty`检查可遍历集合是否包含元素。如果集合中有元素，则显示 true，否则显示 false。

**Example :**

```scala
// Scala program of Size info operation

// Creating object
object Sizeinfo
{

// Main method
    def main(args: Array[String])
    {

// Creating a map
        val q = Map("gfg" -> "cs", "nidhi" -> "geek",
                    "geeta" -> "coder")

// Applying Size info operation
        val r = q.size

// Displays size of the Map
        println(r)
    }
}
```

**Output:**

```scala
3
```

这里，利用`size`来评估可遍历集合的大小。

**Example :**

```scala
// Scala program of Size info operation

// Creating object
object Sizeinfo
{

// Main method
    def main(args: Array[String])
    {

// Creating a map
        val q = Map("gfg" -> "cs", "nidhi" -> "geek",
                    "geeta" -> "coder")

// Applying Size info operation
        val r = q.hasDefiniteSize

// Displays true if number of
        // elements in Map are finite
        println(r)
    }
}
```

**Output:**

```scala
true
```

这里，`hasDefiniteSize`用于检查可遍历集合是否有有限元。如果集合是有限的，则返回 true，否则返回 false。

## Element retrieval operations

Element retrieval operations 包括 `last`、`head`、`lastOption`、`headOption` 和 `find`。这些操作用于检索可遍历集合的第一个或最后一个元素，或检索符合给定条件的第一个元素。

**Example :**

```scala
// Scala program of Element
// retrieval operation

// Creating object
object Retrieval
{

// Main method
    def main(args: Array[String])
    {

// Creating a Set of numbers
        val x = Set(12, 13, 14, 15)

// Applying element retrieval
        // operation
        val y = x.lastOption

// Displays last element
        // of the Set
        println(y)
    }
}
```

**Output:**

```scala
Some(15)
```

这里，可遍历的最后一个元素由`lastOption`返回。必须对指定的集合进行排序，如果集合中没有元素，则返回 `None`。

**Example :**

```scala
// Scala program of Element
// retrieval operation

// Creating object
object Retrieval
{

// Main method
    def main(args: Array[String])
    {

// Creating a Set of numbers
        val x = Set(12, 13, 14, 15)

// Applying element retrieval
        // operation
        val y = x.last

// Displays last element
        // of the Set
        println(y)
    }
}
```

**Output:**

```scala
15
```

这里，`last`将返回所述集合的最后一个元素。集合必须是有序的，如果它不是有序的，那么会返回一些随机元素。

**Example :**

```scala
// Scala program of Element
// retrieval operation

// Creating object
object Retrieval
{

// Main method
    def main(args: Array[String])
    {

// Creating a List of numbers
        val q = List(12, 24, 36, 48)

// Applying element retrieval
        // operation
        val r = q.head

// Displays first element
        // of the List
        println(r)
    }
}
```

**Output:**

```scala
12
```

这里，`head`将返回可遍历集合的第一个元素，如果它是有序的，并且如果该集合不是有序的，则返回任何随机元素。

**Example :**

```scala
// Scala program of Element
// retrieval operation

// Creating object
object Retrieval
{

// Main method
    def main(args: Array[String])
    {

// Creating a List of numbers
        val x = List(8, 10, 21, 17, 29)

// Applying element retrieval
        // operation
        val y = x.find(_ % 3 == 0)

// Displays first element
        // matching the condition
        println(y)
    }
}
```

**Output:**

```scala
Some(21)
```

在这里，`find`将检索集合的第一个元素，该元素与所述条件相匹配。

**Example :**

```scala
// Scala program of Element
// retrieval operation

// Creating object
object Retrieval
{

// Main method
    def main(args: Array[String])
    {

// Creating List of numbers
        val p = List(7, 9, 11, 19, 21)

// Creating a empty List
        val q = List()

// Applying element retrieval
        // operation
        val r = p.headOption
        val s = q.headOption

// Displays first element
        // if the List is not empty
        println(r)
        println(s)
    }
}
```

**Output:**

```scala
Some(7)
None
```

这里，`headOption`返回有序集合的第一个元素，但是如果集合为空，则返回`None`。