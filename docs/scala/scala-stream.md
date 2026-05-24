# 斯卡拉溪

> 原文:[https://www.geeksforgeeks.org/scala-stream/](https://www.geeksforgeeks.org/scala-stream/)

流是一个惰性列表，其中元素只有在需要时才被评估。这是 scala 的一个特性。Scala 支持惰性计算。它提高了我们程序的性能。流具有与[列表](https://www.geeksforgeeks.org/scala-lists/)相同的性能特征。

**语法:**

```scala
val str = 1 #:: 2 #:: 3 #:: Stream.empty
```

在 scala 中，List 可以用**:**运算符构造，而 Stream 可以用**#:**运算符方法构造，使用表达式末尾的 `Stream.empty`。在上面的语法中，这个流的头是 1，它的尾是 2 和 3。

#### 对流的操作

**创建流:**下面是在 Scala 中创建流的例子。
T3】例:

```scala
// Program to creating an empty stream

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Creating stream
        val stream = 1 #:: 2#:: 8 #:: Stream.empty 
        println(stream) 
    } 
}
```

**输出:**

```scala
Stream(1, ?)
```

在上面的输出中，我们可以看到第二个元素没有被求值。这里，显示一个问号来代替元素。Scala 直到需要时才计算列表。尾部没有打印，因为还没有计算。流被指定为延迟计算。

**使用 Stream.cons 创建流:**我们也可以使用 Stream.cons 创建流。一个包`import scala.collection.immutable.Stream.cons`用于创建流。

**示例:**

```scala
// Program to creating an stream
// using cons
import scala.collection.immutable.Stream.cons

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Creating stream
        val stream2: Stream[Int] = cons(1, cons(2, cons(3, Stream.empty) ) )
        println(s"Elements of stream2 = ${stream2}")
    } 
}
```

**输出:**

```scala
Elements of stream2 = Stream(1, ?)
```

**对流使用 take 函数:** take 函数用于从流中提取元素。下面是使用 take 函数的例子。

**示例:**

```scala
// Program to Using take function on stream

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Creating stream
        val stream = 1 #:: 2#:: 8 #:: Stream.empty 
        println(stream) 

        // Taking elements from stream
        print("Take first 2 numbers from stream = ")
        stream.take(2).print
        print("\nTake first 10 numbers from stream2 = ")
        stream.take(10).print
    } 
}
```

**输出:**

```scala
Stream(1, ?)
Take first 2 numbers from stream = 1, 2, empty
Take first 10 numbers from stream2 = 1, 2, 8, empty
```

当我们想从一个流中获取 10 个数字时，尽管它只包含 3 个元素，但它并没有抛出任何 IndexOutOfBoundsException。

**对流使用映射函数:**映射函数用于对流执行操作。

**示例:**

```scala
// Scala program to using map function on stream

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Creating stream
        val stream = 1 #:: 2#:: 8 #:: Stream.empty 
        println(stream) 

        // map elements from stream
        println(stream.map{_+5}) 
    } 
}
```

**输出:**

```scala
Stream(1, ?)
Stream(6, ?)
```

在上面的例子中，通过使用 map 函数，我们将输入集合转换为新的输出集合。

**初始化一个空流:**下面的代码展示了如何初始化一个空流。
**例:**

```scala
// Program to create empty stream

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Creating empty stream
        val emptyStream: Stream[Int] = Stream.empty[Int]
        println(s"Empty Stream = $emptyStream")
    } 
}
```

**输出:**

```scala
 Empty Stream = Stream()
```