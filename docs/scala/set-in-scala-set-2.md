# 在 Scala 中设置|设置-2

> 原文:[https://www.geeksforgeeks.org/set-in-scala-set-2/](https://www.geeksforgeeks.org/set-in-scala-set-2/)

**先决条件:** [集在斯卡拉|集-1](https://www.geeksforgeeks.org/set-in-scala-set-1/)

<center>**Adding items in Mutable Set**</center>

 **In ***Set***, We can only add new elements in mutable set. **+=, ++==** and `**add()**` method is used to add new elements when we are working with mutable set in mutable collection and += is used to add new elements when we are working with *mutable set* in immutable collection.

**例 1:**

```scala
// Scala program to illustrate how to  
// add items using +=, ++== and add() 
// method in mutable set with mutable 
// collection
import scala.collection.mutable._

object Main
{
    def main(args: Array[String])
    {

        // Creating and initilazing set
        var myset = Set("G", "Geek", "for")
        println("Set before addition "+ 
                "of new elements:")
        println(myset)

        // Adding new element in set 
        // using += and ++== 
        myset += "Geeks"

        // Here, "G" is already present in the
        // Set so, "G" is not added in set
        myset ++== List("Geeks12", "geek23", "G")

        // Adding elements using add() method
        myset.add("GeeksforGeeks")
        myset.add("geeksForgeeks100")
        println("\nSet after addition of new elements:")
        println(myset)
    }
}
```

**输出:**

```scala
Set before addition of new elements:
Set(for, G, Geek)

Set after addition of new elements:
Set(geek23, for, Geeks, G, Geek, Geeks12, geeksForgeeks100, GeeksforGeeks)

```

**例 2:**

```scala
// Scala program to illustrate how 
// to add items using += operator in
// mutable set with immutable collection
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initializing mutable set
        var myset = Set("G", "Geek", "for")
        println("Set before addition" +
                " of new elements:")
        println(myset)

        // Adding new element in set 
        // using += operator
        myset += "GeeksforGeeks"
        myset += "geeks1000"

        println("\nSet after addition " +
                "of new elements:")
        println(myset)
    }
}
```

**输出:**

```scala
Set before addition of new elements:
Set(G, Geek, for)

Set after addition of new elements:
Set(for, Geek, G, geeks1000, GeeksforGeeks)

```

<center>**Removing elements from the Mutable set**</center>

 **In Set, We can only remove elements in the mutable set. **-=** and **–=** methods are used to delete elements and we can also use `**retain()**`, `**clear()**`, and `**remove()**` methods to delete elements when we are working with *mutable set* in the mutable collection. -= operator is used to delete elements when we are working with *mutable set* in immutable collection.

**例 1:**

```scala
// Scala program to illustrate
// how to delete items using -= 
// and --= methods in mutalbe set 
// with mutable collection
import scala.collection.mutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initilazing 
        //mutable set
        var myset = Set(100, 400, 500, 
                        600, 300, 800)
        println("Set before deletion:")
        println(myset)

        // Deleting elements in set 
        // using -= and --= methods
        myset -= 600
        myset --= List(300, 100)
        println("\nSet after deletion:")
        println(myset)

    }
}
```

**输出:**

```scala
Set before deletion:
Set(300, 100, 800, 500, 600, 400)

Set after deletion:
Set(800, 500, 400)

```

**例 2:**

```scala
// Scala program to illustrate 
// how to delete items using 
// retain(), and clear() methods
// in mutalbe set with mutable 
// collection
import scala.collection.mutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initializing
        // mutable set
        var myset1 = Set(100, 400, 500,
                            600,300, 800)
        var myset2 = Set(11, 44, 55, 66, 77)
        println("Set before deletion:")
        println(myset1)
        println(myset2)

        // Deleting elements in set 
        // using retain() method
        myset1.retain(_>500)
        println("\nSet after using retain()" +
                                " method:")
        println(myset1)

        // Deleting elements in set 
        // using clear() method
        myset2\. clear
        println("\nSet after using clear() method:")
        println(myset2)
    }
}
```

**输出:**

```scala
Set before deletion:
Set(300, 100, 800, 500, 600, 400)
Set(66, 55, 11, 44, 77)

Set after using retain() method:
Set(800, 600)

Set after using clear() method:
Set()

```

<center>**Adding items in immutable Set**</center>

 **In **immutable set**, We cannot add elements, but we can use **+** and **++** operators to add element from the immutable set and store the result into a new variable. Here, + is used to add single or multiple elements and ++ is used to add multiple elements defined in another sequence and in concatenation of immutable set.

**示例:**

```scala
// Scala program to illustrate how 
// to add elements in immutable set
import scala.collection.immutable._

object Main
{
    def main(args: Array[String])
    {

        // Creating and initilazing 
        // immutable set
        val myset1 = Set(100, 400, 500,
                          600,300, 800)
        val myset2 = Set(11, 44, 55, 66, 77)
        println("Set before addition:")
        println(myset1)
        println(myset2)
        println("\nSet after addition:")

        // Add single element in myset1 
        // and create new Set
        val S1 = myset1 + 900
        println(S1)

        // Add multiple elements in myset1 
        // and create new Set
        val S2 = myset1 + (200, 300)
        println(S2)

        // Add another list into myset1 
        // and create new Set
        val S3 = myset1 ++ List(700, 1000)
        println(S3)

        // Add another set myset2 into 
        // myset1 and create new Set
        val S4 = myset1 ++ myset2
        println(S4)
    }
}
```

**输出:**

```scala
Set before addition:
Set(500, 600, 800, 300, 400, 100)
Set(77, 44, 66, 11, 55)

Set after addition:
Set(500, 900, 600, 800, 300, 400, 100)
Set(500, 600, 800, 300, 400, 200, 100)
Set(500, 700, 1000, 600, 800, 300, 400, 100)
Set(500, 77, 44, 66, 600, 11, 55, 800, 300, 400, 100)

```

<center>**Removing elements from the immutable set**</center>

 **In **immutable set**, We cannot remove elements, but we can use **–** and **—** operators to remove elements from the immutable set and store the result into a new variable. Here, – operator is used to remove one or more elements and — operator is used to remove multiple elements defined in another sequence.

**示例:**

```scala
// Scala program to illustrate how 
// to remove elements in immutable set
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initilazing
        // immutable set
        val myset = Set(100, 400, 500, 600, 
                        300, 800, 900, 700)
        println("Set before deletion:")
        println(myset)

        println("\nSet after deletion:")

        // Remove single element in myset and 
        // Result store into new variable
        val S1 = myset - 100
        println(S1)

        // Remove multiple elements from myset 
        // Result store into new variable
        val S2 = myset - (400, 300)
        println(S2)

        // Remove another list from myset
        // Result store into new variable
        val S3 = myset -- List(700, 500)
        println(S3)
    }
}
```

**输出:**

```scala
Set before deletion:
Set(500, 900, 700, 600, 800, 300, 400, 100)

Set after deletion:
Set(500, 900, 700, 600, 800, 300, 400)
Set(500, 900, 700, 600, 800, 100)
Set(900, 600, 800, 300, 400, 100)

```

<center>**Set Operations**</center>

 **Now we will see some of the basic **mathematical operations** on the Set like Union, Intersection, and Difference.

1.  **联合:**在这种情况下，我们可以简单地将一个集合与其他集合相加。由于集合本身不允许任何重复条目，因此我们不需要考虑公共值。要执行 union，我们使用 union()方法。
2.  **交集:**要从两个集合中获取公共值，我们使用 intersect()方法。它返回一个包含两个集合中所有公共值的新集合。
3.  **差:**为了得到两个集合的差，我们使用 diff()方法。它返回一个集合，该集合包含所有不存在于 my stat2 中的。

**示例:**

```scala
// Scala program to illustrate union, 
// intersection, and difference on Set 
import scala.collection.immutable._

object Main 
{
    def main(args: Array[String]) 
    {

        // Creating and initializing set
        val myset1 = Set(11, 22, 33, 44, 
                        55, 66, 77, 111)
        val myset2 = Set(88, 22, 99, 44,
                            55, 66, 77)

        // To find intersection 
        val S1 = myset1.intersect(myset2)
        println("Intersection:")
        println(S1)

        // To find the symmetric difference 
        val S2 = myset1.diff(myset2)
        println("\nDifference:")
        println(S2)

        // To find union
        val S3 = myset1.union(myset2)
        println("\nUnion:")
        println(S3)
    }
}
```

**输出:**

```scala
Intersection:
Set(77, 22, 44, 66, 55)

Difference:
Set(33, 11, 111)

Union:
Set(88, 33, 77, 22, 44, 66, 11, 99, 55, 111)

```**********