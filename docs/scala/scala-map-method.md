# Scala | map()方法

> 原文:[https://www.geeksforgeeks.org/scala-map-method/](https://www.geeksforgeeks.org/scala-map-method/)

Scala 中的集合是一种保存一组对象的数据结构。集合的例子包括数组、列表等。我们可以使用几种方法对这些集合应用一些转换。Scala 提供的一种广泛使用的方法是 **map()** 。
**关于地图的重要要点()方法**:

*   map()是一个[高阶函数](https://www.geeksforgeeks.org/higher-order-functions-currying/)。
*   每个集合对象都有 map()方法。
*   map()将某个函数作为参数。
*   map()将函数应用于源集合的每个元素。
*   map()返回与源集合类型相同的新集合。

**语法**:

```scala
collection = (e1, e2, e3, ...)

//func is some function
collection.map(func)

//returns collection(func(e1), func(e2), func(e3), ...)

```

**例 1** :使用自定义功能

```scala
// Scala program to
// transform a collection
// using map()

//Creating object
object GfG
{

    // square of an integer
    def square(a:Int):Int
    =
    {
        a*a
    }

    // Main method
    def main(args:Array[String])
    {
        // source collection
        val collection = List(1, 3, 2, 5, 4, 7, 6)

        // transformed collection
        val new_collection = collection.map(square)

        println(new_collection)

    }

}
```

**Output:**

```scala
List(1, 9, 4, 25, 16, 49, 36)

```

在上面的例子中，我们将用户定义的函数**平方**作为参数传递给**地图()**方法。将创建一个新的集合，其中包含原始集合的元素方块。源集合不受影响。

**例 2** :使用匿名函数

```scala
// Scala program to
// transform a collection
// using map()

//Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
        // source collection
        val collection = List(1, 3, 2, 5, 4, 7, 6)

        // transformed collection
        val new_collection = collection.map(x => x * x )

        println(new_collection)
    }
}
```

**Output:**

```scala
List(1, 9, 4, 25, 16, 49, 36)

```

在上面的例子中，一个[匿名函数](https://www.geeksforgeeks.org/anonymous-functions-in-scala/)作为参数传递给了**映射()**方法，而不是定义一个整函数进行平方运算。这种方法减少了代码大小。