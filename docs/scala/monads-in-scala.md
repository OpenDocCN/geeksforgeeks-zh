# 标量中的单子

> 原文:[https://www.geeksforgeeks.org/monads-in-scala/](https://www.geeksforgeeks.org/monads-in-scala/)

在 Scala 中，**单子**是执行连续计算的构造。它是一个覆盖另一个对象的对象。值得注意的是，在这里，某一步操作的输出是另一个计算的输入，它是所述程序最近一步的父项。*单子*既不是一个类，也不是一个特质，它是一个概念。Scala 的最大集合是*单子*但是并不是所有的*单子*都是集合，有几个*单子*是 Scala 中类似 [*选项*](https://www.geeksforgeeks.org/scala-option/) 的容器。简而言之，我们可以说在 Scala 中，实现*映射*以及 [*flatMap()*](https://www.geeksforgeeks.org/scala-flatmap-method/) 的数据类型，如选项、列表等。被称为*单子*。

### 单子提供的操作

对象由*单子*包围，因为它产生以下两个函数:

1.  **unit() :** 就像 Java 中的 void 一样，不返回任何数据类型。
2.  **flatMap() :** 它与 Scala 中的 Map()类似，但它返回一个序列来代替返回单个组件。

让我们看一个例子来明确地说明它。

```scala
var x = Seq("Geeks", "For", "Geeks")

```

让我们对给定的序列应用 map()。

```scala
// Applying map()
 var y = x.map(_.toUpperCase)
// Output
List(GEEKS, FOR, GEEKS)

```

现在，让我们对给定的序列应用 flatMap()。

```scala
// Applying flatMap()
var z = x.flatMap(_.toUpperCase)
// Output
List(G, E, E, K, S, F, O, R, G, E, E, K, S)

```

因此，当*平面图*应用于上述序列时，将返回一个列表，其中内部分组被移除，并生成一个序列。

**注:**支持*地图*以及*平面地图*的集合称为*一元*。现在，让我们来看一些 Scala 中*单子*的例子。

支持*地图*以及*平面图*的收藏示例。
**例:**

```scala
// Scala program of Monads

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of numbers
        val list1 = List(1, 2, 3, 4)
        val list2 = List(5, 6, 7, 8)

        // Applying 'flatMap' and 'map'
        val z = list1 flatMap { q => list2 map {
                r => q + r
        }
        }

        // Displays output
        println(z)

    }
} 
```

**Output:**

```scala
List(6, 7, 8, 9, 7, 8, 9, 10, 8, 9, 10, 11, 9, 10, 11, 12)

```

现在让我们看看，输出是如何计算的。

> //应用地图()我们得到如下列表
> 列表(List((1+5)、(1+6)、(1+7)、(1+8))、List((2+5)、(2+6)、(2+7)、(2+8))、
> 列表((3+5)、(3+6)、(3+7)、(3+8))、List((4+5)、(4+6)、(4+7)、(4+8)))

在我们得到评估后，

> 列表(列表(6，7，8，9)，列表(7，8，9，10)，列表(8，9，10，11)，列表(9，10，11，12))

因此，我们得到一个列表列表，在应用 *map()* 之后，对于每个操作，我们有一个不同的列表，现在让我们应用 *flatMap()* 。

> //应用 flatMap()我们得到如下列表
> 列表(6，7，8，9，7，8，9，10，8，9，10，11，9，10，11，11，12)

因此，当我们应用 *flatMap()* 时，内部分组被移除。

**示例:**

```scala
// Scala program of Monads

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of numbers
        val x = (1 to 3).toList
        val y = (1 to 7 by 2).toList

        // Applying 'flatMap'and 'map'
        val z = x flatMap { s => y map { 
                    t => s * t 

        }
        }

        // Displays output
        println(z)
    }
} 
```

**Output:**

```scala
List(1, 3, 5, 7, 2, 6, 10, 14, 3, 9, 15, 21)

```

这里，列表(x) = (1，2，3)和列表(y) = (1，3，5，7)现在，让我们看看输出是如何计算的。

> //应用 map()我们得到如下列表
> List(List((1*1)、(1*3)、(1*5)、(1*7))、List((2*1)、(2*3)、(2*5)、(2*7))、
> List((3*1)、(3*3)、(3*5)、(3*7)))

经过评估后，我们得到，

> 列表(列表(1，3，5，7)，列表(2，6，10，14)，列表(3，9，15，21))

现在，让我们应用 flatMap()。

```scala
// Applying flatMap() we get a list like below
List(1, 3, 5, 7, 2, 6, 10, 14, 3, 9, 15, 21)

```

因此，内部分组被移除。