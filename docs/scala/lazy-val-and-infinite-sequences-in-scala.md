# Scala 中的惰性值和无限序列

> 原文:[https://www . geesforgeks . org/lazy-val-和-无限序列-in-scala/](https://www.geeksforgeeks.org/lazy-val-and-infinite-sequences-in-scala/)

val 和**Lazy**val 存在于 Scala 中。lazy 关键字将 val 更改为 lazy 初始化。惰性初始化意味着每当对象创建看起来很昂贵时，惰性关键字可以放在 val 之前。这使它具有在第一次使用时初始化的优势，即表达式 inbound 不会立即计算，而是在第一次访问时计算一次。

**例:**

```scala
// Scala program of Lazy val

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        lazy val geek = {

            println ("Initialization for the first time")
            12
        }
        // Part 1
        println(geek)

        // Part 2
        print(geek)
    } 
}     

```

**输出:**

```scala
Initialization for the first time
12
12

```

在上面的代码中,“geek”是一个懒惰的 val，所以第一次被访问时，它返回

```scala
Initialization for the first time
12
```

但是第二次打印时，它只返回了

```scala
12
```

因为它是缓存的结果。

当我们在 val 关键字前使用 lazy 关键字时，块表达式用于初始化变量——“geek”。为了在 Scala 中使用该块，表达式序列包含在 **{ }** 中。所以，值“12”是 block 的值，赋值表达式值是 Unit，这实际上是 Java 中的一个 void 类型。

## 无限序列

Scala 的列表是序列。此外，这些列表是**严格序列**，这意味着列表元素是预先构建的。但是也有非严格的序列，其中元素是按照要求构造的。列表是通过连接 cons 单元格创建的。

这样的情况有 2 种:

*   ```scala
    12 ::Nil
    ```

    这里，con 单元格有值，尾列表为空。这里的列表只是一个元素。

    ```scala
    List[Int] = List(12)
    ```

*   ```scala
    12 : 22 : Nil
    ```

    在这里，cons 单元格有一个值和另一个列表作为尾巴。

    ```scala
    List[Int] = List(22)
    ```

**::** 符号是 cons(构造)运算符。我们调用 *cons* 运算符， *Nil* 是一个列表。这就是列表增长的方式。

创建这样的列表有 3 种方式:

*   **代码 1 :**

    ```scala
    val geek = 6 ::23 ::45 ::Nil

        print(geek)
    ```

    **输出:**

    ```scala
    List(6, 23, 45)
    ```

*   **代码 2:**T2】

    T21】输出:

    ```scala
    List(6, 23, 45)
    ```

*   T24】代码 3:

    ```scala
    val geek = (((Nil.::(45)).::(23)).::(6))

        print(geek)
    ```

    T29】输出:

    ```scala
    List(6, 23, 45)
    ```

**例:**

```scala
// Scala program to merge lists 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        var a = 5

        def fun() = { 
            a += 1; 
            a 
        }

        lazy val geek = Stream.continually( fun() )

        (geek take 10) foreach {
            x => println(x)
        }
    } 
}     

```

**输出:**

```scala
6
7
8
9
10
11
12
13
14
15

```

**fun()** 方法转换为函数。*流.续()*法创造无限流。它接受函数，并且每当访问每个元素时，fun()函数只在那个时候被调用来计算那个元素。这种按需执行的功能被称为 **Thunk** ，一旦计算出来，它就进入缓存以供进一步使用，这被称为**记忆**。