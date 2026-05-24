# 在 Scala 中设置|设置-1

> 原文:[https://www.geeksforgeeks.org/set-in-scala-set-1/](https://www.geeksforgeeks.org/set-in-scala-set-1/)

一套**套**是只包含 ***独有物品*** 的集合。集合的唯一性由集合所包含的类型的==方法定义。如果您试图在集合中添加重复的项目，则集合会悄悄地放弃您的请求。
**语法:**

```scala
// Immutable set
val variable_name: Set[type] = Set(item1, item2, item3)
or
val variable_name = Set(item1, item2, item3)

// Mutable Set
var variable_name: Set[type] = Set(item1, item2, item3)
or
var variable_name = Set(item1, item2, item3)

```

**Scala 中关于集合的几个重要点**

*   在 Scala 中，*可变的*和*不可变的集合*都是可用的。可变集是那些对象的值被改变的集合，但是在不可变集中，对象的值本身不被改变。
*   *默认情况下在 Scala 中设置的*是**不可变的**。
*   在 Scala 中，不可变集定义在 Scala.collection .不可变. package 下，可变集定义在 Scala . collection . mutatable . package 下。
*   我们还可以在 Scala . collection . unvariable . package _ 下定义一个可变集合，如下例所示。
*   器械包有各种添加、清除、调整大小等方法。以提高器械包的使用率。
*   在 Scala 中，我们可以创建空集合。
    **语法:**

    ```scala
    // Immutable empty set
    val variable_name = Set()

    // Mutable empty set
    var variable_name = Set()
    ```

**例 1:**

```scala
// Scala program to illustrate the 
// use of immutable set
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initializing immutable sets
        val myset1: Set[String] = Set("Geeks", "GFG", 
                            "GeeksforGeeks", "Geek123")
        val myset2 = Set("C", "C#", "Java", "Scala", 
                                          "PHP", "Ruby")

        // Display the value of myset1
        println("Set 1:")
        println(myset1)

        // Display the value of myset2 using for loop
        println("\nSet 2:")
        for(myset<-myset2)
        {
            println(myset)
        }
    }
}
```

**输出:**

```scala
Set 1:
Set(Geeks, GFG, GeeksforGeeks, Geek123)

Set 2:
Scala
C#
Ruby
PHP
C
Java

```

**例 2:**

```scala
// Scala program to illustrate the 
// use of mutable set
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String])
    {

        // Creating and initializing mutable sets
        var myset1: Set[String] = Set("Geeks", "GFG", 
                            "GeeksforGeeks", "Geek123")
        var myset2 = Set(10, 100, 1000, 10000, 100000)

        // Display the value of myset1
        println("Set 1:")
        println(myset1)

        // Display the value of myset2 
        // using a foreach loop
        println("\nSet 2:")
        myset2.foreach((item:Int)=>println(item))
    }
}
```

**输出:**

```scala
Set 1:
Set(Geeks, GFG, GeeksforGeeks, Geek123)

Set 2:
10
100000
10000
1000
100

```

**例 3:**

```scala
// Scala program to illustrate the 
// use of empty set
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating empty sets
        val myset = Set()

        // Display the value of myset
        println("The empty set is:")
        println(myset)
    }
}
```

**输出:**

```scala
The empty set is:
Set()

```

#### 排序集

在集合中，**排序集合**用于按排序顺序从集合中获取值。SortedSet 只适用于不可变集合。
T3】例:

```scala
// Scala program to get sorted values 
// from the set
import scala.collection.immutable.SortedSet 

object Main
{
    def main(args: Array[String]) 
    {

        // Using SortedSet to get sorted values
        val myset: SortedSet[Int] = SortedSet(87, 0, 3, 45, 7, 56, 8,6)
        myset.foreach((items: Int)=> println(items))
    }
}
```

**输出:**

```scala
0
3
6
7
8
45
56
87

```