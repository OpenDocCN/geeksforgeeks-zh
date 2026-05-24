# Scala 迭代器映射()方法示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-map-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-map-method-with-example/)

**map()** 方法属于抽象迭代器类的具体值成员。它通过对所述迭代器的每个元素应用一个函数来构建一个新的迭代器。

**方法定义:**

```scala
def map[B](f: (A) => B): Iterator[B]

```

其中， *B* 是返回的迭代器的元素类型， *f* 是要应用于迭代器每个元素的函数。
**返回类型:**
将函数应用于给定迭代器的每个元素后，从指定的迭代器返回一个新的迭代器。
**示例#1:**

```scala
// Scala program of map()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 19, 21)

        // Applying map method
        val iter1 = iter.map(x=>{x*3})

        // Applying next method
        val result = iter1.next()

        // Again applying next method
        val result1 = iter1.next()

        // Displays output
        println(result)
        println(result1)

    }
}
```

**Output:**

```scala
9
18

```

这里，该函数应用于所述迭代器的所有元素，我们可以在这里看到前两个元素，其中三乘以每个元素，类似地，它乘以所述迭代器的所有元素，得到一个新的迭代器。
**例 2:**

```scala
// Scala program of map()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 19, 21)

        // Applying map method
        val iter1 = iter.map(y=>{y/3})

        // Applying next method
        val result= iter1.next()

        // Again applying next method
        val result1= iter1.next()

        // Displays output
        println(result)
        println(result1)

    }
}
```

**Output:**

```scala
1
2

```

这里，前两个元素将被三除，并将结果放入一个新的迭代器中。