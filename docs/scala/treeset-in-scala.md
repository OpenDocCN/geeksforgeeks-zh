# Scala 中的树集

> 原文:[https://www.geeksforgeeks.org/treeset-in-scala/](https://www.geeksforgeeks.org/treeset-in-scala/)

[Set](https://www.geeksforgeeks.org/set-in-scala-set-1/) 是一种数据结构，允许我们存储唯一的元素。元素的顺序不能由集合来保证，而树集合会使元素按照给定的顺序排列。在 Scala 中，TreeSet 有两个版本:`scala.collection.immutable.TreeSet`和`scala.collection.mutable.TreeSet`。

**语法:**

```scala
var TreesetName = TreeSet(element1, element2, element3, ....) 
```

#### 使用 TreeSet 执行的操作

**初始化树集:**

下面是创建或初始化 TreeSet 的示例。
**例:**

```scala
// Scala program of Initializing TreeSet 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize a TreeSet") 

        // Creating TreeSet 
        val treeSet: TreeSet[String] = TreeSet("Geeks", 
                                    "GeeksForGeeks", "Author") 
        println(s"Elements are = $treeSet") 
    } 
} 
```

**输出:**

```scala
Initialize a TreeSet
Elements are = TreeSet(Author, Geeks, GeeksForGeeks)
```

**检查树集中的具体元素:**
**示例:**

```scala
// Scala program of Check specific elements in TreeSet 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize a TreeSet") 

        // Creating TreeSet 
        val treeSet: TreeSet[String] = TreeSet("Geeks", 
                                "GeeksForGeeks", "Author") 
        println(s"Elements are = $treeSet") 

        // Checking 
        println(s"Element Geeks = ${treeSet("Geeks")}") 
        println(s"Element Student = ${treeSet("Student")}") 
    } 
} 
```

**输出:**

```scala
Initialize a TreeSet
Elements are = TreeSet(Author, Geeks, GeeksForGeeks)
Element Geeks = true
Element Student = false
```

**在树集中添加元素:**

我们可以使用 **+** 符号在 TreeSet 中添加一个元素。下面是在 TreeSet 中添加元素的示例。
T3】例:

```scala
// Scala program of adding an element in TreeSet 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize a TreeSet") 

        // Creating TreeSet 
        val ts: TreeSet[String] = TreeSet("Geeks", 
                            "GeeksForGeeks", "Author") 
        println(s"Elements are = $ts") 

        // Adding an element in HashSet 
        val ts1: TreeSet[String] = ts + "GeeksClasses"
        println(s"Adding elements to TreeSet = $ts1") 
    } 
} 
```

**输出:**

```scala
Initialize a TreeSet
Elements are = TreeSet(Author, Geeks, GeeksForGeeks)
Adding elements to TreeSet = TreeSet(Author, Geeks, GeeksClasses, GeeksForGeeks)
```

**在树集中添加两个树集:**

我们可以通过使用++符号来添加两个树集。下面是添加两个 TreeSets 的示例。
**例:**

```scala
// Scala program of adding two TreeSets
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize a TreeSet") 

        // Creating HashSet 
        val ts: TreeSet[String] = TreeSet("Geeks", 
                                "GeeksForGeeks", "Author") 
        println(s"Elements are = $ts") 

        // Adding elements in HashSet 
        val ts1: TreeSet[String] = ts ++ TreeSet[String]("Java", "Scala") 
        println(s"Add more than one TreeSets = $ts1") 
    } 
} 
```

**输出:**

```scala
Initialize a TreeSet
Elements are = TreeSet(Author, Geeks, GeeksForGeeks)
Add more than one TreeSets = TreeSet(Author, Geeks, GeeksForGeeks, Java, Scala)
```

**移除树集中的元素:**

我们可以通过使用–号来移除 TreeSet 中的一个元素。下面是在 TreeSet 中移除元素的示例。
**例:**

```scala
// Scala program of removing element in TreeSet 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize a TreeSet") 

        // Creating HashSet 
        val ts: TreeSet[String] = TreeSet("Geeks", 
                                "GeeksForGeeks", "Author") 
        println(s"Elements are = $ts") 

        // removing elements in HashSet 
        val ts1: TreeSet[String] = ts - "Geeks"
        println(s"remove element from treeset = $ts1") 
    } 
} 
```

**输出:**

```scala
Initialize a TreeSet
Elements are = TreeSet(Author, Geeks, GeeksForGeeks)
remove element from treeset = TreeSet(Author, GeeksForGeeks)
```

**找到两个树集的交集:**

我们可以通过使用&符号来找到两个树集之间的交集。下面是寻找两个树集交集的例子。
**例:**

```scala
// Scala program of finding the intersection
// between two TreeSets 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initialize two TreeSets") 

        // Creating two TreeSet 
        val ts: TreeSet[String] = TreeSet("Geeks", 
                            "GeeksForGeeks", "Author") 
        println(s"Elements of treeset1 are = $ts") 

        val ts1: TreeSet[String] = TreeSet("Java", 
                                    "Geeks", "Scala") 
        println(s"Elements of treeset2 are = $ts1") 

        // finding the intersection between two TreeSets 
        println(s"Intersection of treeSet1 and treeSet2 = ${ts & ts1}") 
    } 
} 
```

**输出:**

```scala
Initialize two TreeSets
Elements of treeset1 are = TreeSet(Author, Geeks, GeeksForGeeks)
Elements of treeset2 are = TreeSet(Geeks, Java, Scala)
Intersection of treeSet1 and treeSet2 = TreeSet(Geeks)
```

**初始化一个空的树集合:**

下面是显示空 TreeSet 的示例。
**例:**

```scala
// Scala program of Initializing an empty TreeSet 
import scala.collection.immutable.TreeSet 

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        // Initializing an empty TreeSet 
        val emptyTreeSet: TreeSet[String] = TreeSet.empty[String] 
        println(s"Empty TreeSet = $emptyTreeSet") 
    } 
} 
```

**输出:**

```scala
Empty TreeSet = TreeSet()
```