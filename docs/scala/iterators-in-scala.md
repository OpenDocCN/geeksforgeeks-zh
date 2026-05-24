# Scala 中的迭代器

> 原文:[https://www.geeksforgeeks.org/iterators-in-scala/](https://www.geeksforgeeks.org/iterators-in-scala/)

**迭代器**是一种逐个访问集合元素的方法。它在语法上类似于一个集合，但在功能上有所不同。为任何集合定义的迭代器不会将整个集合加载到内存中，而是一个接一个地加载元素。因此，当数据对于内存来说太大时，迭代器是有用的。要访问元素，我们可以使用 **hasNext()** 检查是否有可用的元素，使用 **next()** 打印下一个元素。
**语法:**

```scala
val v = Iterator(5, 1, 2, 3, 6, 4)

//checking for availability of next element
while(v.hasNext)

//printing the element
println(v.next)
```

**为集合定义迭代器**

我们可以为任何集合(数组、列表等)定义一个迭代器，并且可以遍历特定集合的元素。
**例:**

```scala
//Scala iterator program
//for defining iterator

//Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        val v = Array(5,1,2,3,6,4)
        //val v = List(5,1,2,3,6,4)

        // defining an iterator
        // for a collection
        val i = v.iterator

        while (i.hasNext)
            print(i.next + " ")
    }
}
```

**输出:**

```scala
5 1 2 3 6 4 
```

**获取元素的方式**

1.  **Using while loop:** Simplest way to access elements is to use *while* loop along with *hasNext* and *next* methods.

    ```scala
    // Scala iterator program
    // for accessing using while

    // Creating object
    object GFG
    {
        // Main method
        def main(args:Array[String])
        {
            // defining iterator
            val i = Iterator(5, 1, 2, 3, 6, 4)

            /*
            OR
            val v = List(5, 1, 2, 3, 6, 4)
            val i = v.iterator
            */

            // accessing elements using while loop
            while (i.hasNext)
                println(i.next)
        }
    }
    ```

    **输出:**

    ```scala
    5
    1
    2
    3
    6
    4

    ```

2.  **Using foreach action:** We can make use of *foreach* to print elements by passing *println* function as parameter. Note that *foreach* is a higher order function that takes another function as parameter. In other words, *println* function is applied on every element.

    ```scala
    // Scala iterator program
    // for accessing using foreach

    // Creating object
    object GFG
    {
        // Main method
        def main(args:Array[String])
        {
            // defining iterator
            val i = Iterator(5, 1, 2, 3, 6, 4)

            /*
            OR
            val v = List(5, 1, 2, 3, 6, 4)
            val i = v.iterator
            */

            // accessing elements using foreach
            i foreach println
            // same as i.foreach(println)
        }
    }
    ```

    **输出:**

    ```scala
    5
    1
    2
    3
    6
    4

    ```

3.  **用于循环:**另一种简单的方法是将*用于*循环。它的工作方式与使用循环的*访问任何集合的元素非常相似。*

```scala
// Scala iterator program
// for accessing using for

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        // defining iterator
        val i = Iterator(5, 1, 2, 3, 6, 4)

        /*
        OR
        val v = List(5, 1, 2, 3, 6, 4)
        val i = v.iterator
        */

        // accessing elements using for loop
        for(k <- i) println(k)
    }
}
```

**输出:**

```scala
5
1
2
3
6
4

```

**寻找具有最小值和最大值的元素**

*   Using **built-in** functions *min* and *max* Iterators can be traversed only once. Therefore, we should redefine the iterator after finding the maximum value.

    ```scala
    // Scala iterator program for minimum
    // and maximum valued element
    // using built-in methods

    // Creating object
    object GFG
    {
        // Main method
        def main(args:Array[String])
        {
            // defining iterator
            val i1 = Iterator(5, 1, 2, 3, 6, 4)

            // calling max function
            println("Maximum: "+ i1.max)

            // redefining iterator
            val i2 = Iterator(5, 1, 2, 3, 6, 4)

            // calling min function
            println("Minimum: "+ i2.min)
        }
    }
    ```

    **输出:**

    ```scala
    Maximum: 6
    Minimum: 1
    ```

*   **用户自定义**功能返回最小值和最大值。我们可以根据自己的方便定义自己的纯函数来打印最小值和最大值元素。

下面的代码打印最小值元素:

```scala
// Scala iterator program
// for minimum valued element
// user defined method

// Creating object
object GFG
{
    // parameter is an Iterator of Int
    // returning Int value
    def small(ite : Iterator[Int]) : Int = 
    {

        // storing first value of collection
        var mn = ite.next

        for(i <- ite)
        if(i < mn) mn = i

        // returning     
        mn

    }

    // Main method
    def main(args:Array[String])
    {
        // defining iterator
        val i = Iterator(5, 1, 2, 3, 6, 4)

        //calling small function
        println("Minimum: "+ small(i))
    }
}
```

**输出:**

```scala
Minimum: 1
```

下面的代码打印最大值元素:

```scala
// Scala iterator program
// for maximum valued element
// user defined method

// Creating object
object GFG
{
    // parameter is an Iterator of Int
    // returning Int value
    def large(ite: Iterator[Int]): Int =
    {

        // storing first value of collection
        var mx = ite.next

        for(i <- ite)
        if(i > mx) mx = i

        // returning
        mx
    }

    // Main method
    def main(args:Array[String])
    {
        // defining iterator
        val i = Iterator(5, 1, 2, 3, 6, 4)

        // calling large function
        println("Maximum: "+ large(i))
    }
}
```

**输出:**

```scala
Maximum: 6
```

**注意:**大()和小()这两个函数都是作为两个独立的代码编写的，以减轻在线编译器的负担。