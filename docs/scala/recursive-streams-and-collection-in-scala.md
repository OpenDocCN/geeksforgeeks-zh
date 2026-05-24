# Scala 中的递归流和集合

> 原文:[https://www . geeksforgeeks . org/Scala 中的递归流和集合/](https://www.geeksforgeeks.org/recursive-streams-and-collection-in-scala/)

递归表单有自己的定义，就像我们在文件夹中有子文件夹一样，文件夹中还可以有子文件夹。递归方法调用自己也是一种递归形式。类似的形式可以用来创建递归流。

**示例 1:** 创建懒惰列表

```scala
// Scala program for resursive stream
// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // second con can be recursive
        lazy val geek = Stream.cons(1, Stream.cons(5, Stream.empty))

        println (geek)

        (geek take 4) foreach {
            x => println(x)

        } 
    } 
} 
```

**输出:**

```scala
Stream(1, ?)
1
5

```

在上面的代码中，第二个 con 是递归的。

**示例 2:** 通过对方法进行递归调用来创建惰性列表

```scala
// Scala program for resursive stream

// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // con can be recursive
        def geek(n: Int): Stream[Int] = Stream.cons(n, geek(n+1))

        // Creating lazy val
        lazy val q = geek(5)

        println(q) 
    } 
} 
```

**输出:**

```scala
Stream(5, ?)
```

**示例 3:** 通过以简单明了的方式递归调用方法来创建一个惰性列表

```scala
// Scala program for resursive stream

// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // recursive stream
        def geek(n: Int):Stream[Int] = n #:: geek(n+1)

        // Lazy value
        lazy val q = geek(5)

        println(q)

    } 
} 
```

**输出:**

```scala
Stream(5, ?)
```

## 流集合

scala 中的流集合非常重要，因为它允许不需要显式删减。声明性地，事情可以使用函数组合器来执行，如 map、filter 和 flatMap。流是懒惰的丢失的集合。

**例 4:**

```scala
// Scala program for stream collection

// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // creating Stream
        def geek(n: Int):Stream[Int] = n #:: geek(n+1)

        lazy val g = geek(0)

        println (g)
        println (g.take(10).mkString(" ; "))
    } 
} 
```

**输出:**

```scala
Stream(0, ?)
0 ; 1 ; 2 ; 3 ; 4 ; 5 ; 6 ; 7 ; 8 ; 9)

```

**示例 5:** 使用过滤器

```scala
// Scala program for filter list

// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating list
        val geek = List(1, 2, 3, 4)

        // Using filter
        val abc = geek filter { x => x > 2 }
        println(abc)
    } 
} 
```

**输出:**

```scala
List(3, 4)
```

过滤器被称为超列表极客。它将函数作为参数，并返回一个布尔值，这是一个函数谓词。每个元素都在函数中运行，并且在函数返回 false 时过滤掉元素。这导致了一个新的名单，原来的“极客”名单是保持持久。

**示例 6:** 以非常简洁的方式使用过滤器

```scala
// Scala program for collection

// creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating list
        val geek = List(1, 2, 3, 4)

        // Filter list
        val abc = geek filter { _ > 2 }
        println(abc)

    } 
} 
```

**输出:**

```scala
List(3, 4)
```

在上面的代码中，不需要命名元素。该元素由一个较短的形式通过 a_ 引用。也不需要限定方法调用。