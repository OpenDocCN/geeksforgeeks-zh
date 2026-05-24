# Scala | reduce()函数

> 原文:[https://www.geeksforgeeks.org/scala-reduce-function/](https://www.geeksforgeeks.org/scala-reduce-function/)

**reduce()** 方法是一个高阶函数，它获取集合(数组、列表等)中的所有元素，并使用*二进制运算*将其组合以产生一个值。有必要确保操作是可交换的和关联的。[匿名函数](https://www.geeksforgeeks.org/anonymous-functions-in-scala)作为参数传递给 reduce 函数。
**语法** :

```scala
val l = List(2, 5, 3, 6, 4, 7)
// returns the largest number from the collection
l.reduce((x, y) => x max y)
```

通过**减少**方法选择数字进行操作的顺序是随机的。这就是为什么不喜欢非交换和非关联操作的原因。
**例:**

## 斯卡拉

```scala
// Scala program to
// print maximum value
// using reduce()

// Creating object
object GfG
{

// Main method
def main(args:Array[String])
{
    // source collection
    val collection = List(1, 3, 2, 5, 4, 7, 6)

    // finding the maximum valued element
    val res = collection.reduce((x, y) => x max y)

    println(res)
}
}
```

**输出:**

```scala
7
```

在上面的程序中，reduce 方法选择随机对，并找出特定对中的最大值。这些值再次相互比较，直到获得单个最大值元素。在 Spark 中处理弹性分布式数据集时，我们通常使用 reduce()方法和 [map()](https://www.geeksforgeeks.org/scala-map-method/) 方法。map()方法帮助我们将一个集合转换为另一个集合，而 reduce()方法允许我们执行一些操作。
**使用地图()和 reduce()查找平均值:**
**示例:**

## 斯卡拉

```scala
// Scala program to
// print average
// using map() and reduce()

//Creating object
object GfG
{

// Main method
def main(args:Array[String])
{
    // source collection
    val collection = List(1, 5, 7, 8)

    // converting every element to a pair of the form (x,1)
    // 1 is initial frequency of all elements
    val new_collection = collection.map(x => (x,1))

    /*
    List((1, 1), (5, 1), (7, 1), (8, 1))
    */

    // adding elements at corresponding positions
    val res = new_collection.reduce( (a,b) => ( a._1 + b._1,
                                            a._2 + b._2 ) )
    /*
    (21, 4)
    */

    println(res)
    println("Average="+ res._1/res._2.toFloat)
}
}
```

**输出** :

```scala
(21, 4)
Average= 5.25
```

在上面的程序中，集合的所有元素都被转换成带有两个元素的[元组](https://www.geeksforgeeks.org/scala-tuple)。元组的第一个元素是数字本身，第二个元素是计数器。最初，所有计数器都设置为 1。输出本身是一个包含两个元素的元组:第一个值是总和，第二个值是元素的数量。
**注**:reduce()方法给出的输出类型与集合的元素类型相同。