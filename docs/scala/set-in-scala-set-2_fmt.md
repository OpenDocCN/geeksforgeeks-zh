# 在 Scala 中设置 | 设置-2

> 原文: [https://www.geeksforgeeks.org/set-in-scala-set-2/](https://www.geeksforgeeks.org/set-in-scala-set-2/)

**先决条件:** [集在斯卡拉 | 集-1](https://www.geeksforgeeks.org/set-in-scala-set-1/)

## Adding items in Mutable Set

在 `Set` 中，我们只能向可变集合（mutable set）中添加新元素。当我们在可变集合（mutable collection）中使用可变集合（mutable set）时，可以使用 `+=`、`++==` 和 `add()` 方法来添加新元素；当我们在不可变集合（immutable collection）中使用可变集合（mutable set）时，可以使用 `+=` 来添加新元素。

### 例 1:

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

### 输出:

```scala
Set before addition of new elements:
Set(for, G, Geek)

Set after addition of new elements:
Set(geek23, for, Geeks, G, Geek, Geeks12, geeksForgeeks100, GeeksforGeeks)
```

### 例 2:

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

### 输出:

```scala
Set before addition of new elements:
Set(G, Geek, for)

Set after addition of new elements:
Set(for, Geek, G, geeks1000, GeeksforGeeks)
```

## Removing elements from the Mutable set

在 `Set` 中，我们只能从可变集合（mutable set）中删除元素。当我们在可变集合（mutable collection）中使用可变集合（mutable set）时，可以使用 `-=` 和 `--=` 方法来删除元素，也可以使用 `retain()`、`clear()` 和 `remove()` 方法来删除元素。当我们在不可变集合（immutable collection）中使用可变集合（mutable set）时，可以使用 `-=` 运算符来删除元素。

### 例 1:

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

### 输出:

```scala
Set before deletion:
Set(300, 100, 800, 500, 600, 400)

Set after deletion:
Set(800, 500, 400)
```

### 例 2:

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
```

# Scala 集合操作

## 在可变集合中删除元素

```scala
// Deleting elements in set 
// using retain() method
myset1.retain(_>500)
println("\nSet after using retain()" +
                        " method:")
println(myset1)

// Deleting elements in set 
// using clear() method
myset2.clear
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

## 在不可变集合中添加元素

在**不可变集合**中，我们不能直接添加元素，但可以使用 `+` 和 `++` 操作符从不可变集合中添加元素，并将结果存储到一个新变量中。这里，`+` 用于添加单个或多个元素，`++` 用于添加另一个序列中定义的多个元素以及连接不可变集合。

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

## 从不可变集合中删除元素

在**不可变集合**中，我们不能直接删除元素，但可以使用 `-` 和 `--` 操作符从不可变集合中删除元素，并将结果存储到一个新变量中。这里，`-` 操作符用于删除一个或多个元素，`--` 操作符用于删除另一个序列中定义的多个元素。

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

## 集合操作

现在我们将看到集合上的一些基本**数学运算**，如并集、交集和差集。

1.  **联合:** 在这种情况下，我们可以简单地将一个集合与其他集合相加。由于集合本身不允许任何重复条目，因此我们不需要考虑公共值。要执行 union，我们使用 `union()` 方法。
2.  **交集:** 要从两个集合中获取公共值，我们使用 `intersect()` 方法。它返回一个包含两个集合中所有公共值的新集合。
3.  **差:** 为了得到两个集合的差，我们使用 `diff()` 方法。它返回一个集合，该集合包含所有不存在于 `myset2` 中的元素。

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
```