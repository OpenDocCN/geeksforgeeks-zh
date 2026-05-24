# Scala 中的列表集

> 原文:[https://www.geeksforgeeks.org/listset-in-scala/](https://www.geeksforgeeks.org/listset-in-scala/)

一个[集合](https://www.geeksforgeeks.org/set-in-scala-set-1/)是一个只包含不可重复的唯一项的集合，一个列表是一个包含不可变数据的集合。在 scala 中，`**ListSet class**`使用基于[列表](https://www.geeksforgeeks.org/scala-lists/)的数据结构实现不可变集。元素以相反的插入顺序存储，这意味着最新的元素位于列表的开头。它保持插入顺序。

Listset 仅用于少量元素。我们可以通过调用构造函数或应用函数`ListSet.empty`来创建空的列表集。它的迭代和遍历方法访问元素的顺序与它们第一次插入的顺序相同。

**语法:**

```scala
var ListSetName = ListSet(element1, element2, element3, ....)  
```

## 使用列表集的操作

**初始化列表集:**下面是创建或初始化列表集的示例。

```scala
// Scala program to Initialize a ListSet 
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initializing an immutable ListSet ")

        // Creating ListSet
        val listSet1: ListSet[String] = ListSet("GeeksForGeeks",
                                            "Article", "Scala")
        println(s"Elements of listSet1 = $listSet1")
    } 
} 
```

**输出:**

```scala
Initializing an immutable ListSet 
Elements of listSet1 = ListSet(Scala, Article, GeeksForGeeks)
```

**检查列表集中的具体元素:**

```scala
// Scala program to Check specific elements in ListSet 
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initializing an immutable ListSet ")

        // Creating ListSet
        val listSet1: ListSet[String] = ListSet("GeeksForGeeks",
                                            "Article", "Scala")
        println(s"Elements of listSet1 = $listSet1")

        println("Check elements of immutable ListSet")

        // Checking element in a ListSet
        println(s"GeeksForGeeks = ${listSet1("GeeksForGeeks")}")
        println(s"Student = ${listSet1("Student")}")
        println(s"Scala = ${listSet1("Scala")}")
    } 
} 
```

**输出:**

```scala
Initializing an immutable ListSet 
Elements of listSet1 = ListSet(Scala, Article, GeeksForGeeks)
Check elements of immutable ListSet
GeeksForGeeks = true
Student = false
Scala = true
```

**在列表集中添加元素:**我们可以使用+运算符在列表集中添加元素。下面是在 ListSet 中添加元素的例子。

```scala
// Scala program to Add an element in a ListSet
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initializing an immutable ListSet ")

        // Creating ListSet
        val listSet1: ListSet[String] = ListSet("GeeksForGeeks",
                                            "Article", "Scala")
        println(s"Elements of listSet1 = $listSet1")

        // Adding element in ListSet
        println("Add element of immutable ListSet ")
        val listSet2: ListSet[String] = listSet1 + "Java"
        println(s"Adding element java to ListSet $listSet2")
    } 
} 
```

**输出:**

```scala
Initializing an immutable ListSet 
Elements of listSet1 = ListSet(Scala, Article, GeeksForGeeks)
Add element of immutable ListSet 
Adding element java to ListSet ListSet(Java, Scala, Article, GeeksForGeeks)
```

**添加两个列表集:**我们可以使用++运算符添加两个列表集。下面是添加两个列表集的例子。

```scala
// Scala program to Add two ListSet
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initializing an immutable ListSet ")

        // Creating ListSet
        val listSet1: ListSet[String] = ListSet("GeeksForGeeks",
                                               "Article", "Scala")
        println(s"Elements of listSet1 = $listSet1")

        // Adding two ListSet
        val listSet2: ListSet[String] = listSet1 ++ ListSet("Java", 
                                                            "Csharp")
        println(s"After adding two lists $listSet2")

    } 
} 
```

**输出:**

```scala
Initializing an immutable ListSet 
Elements of listSet1 = ListSet(Scala, Article, GeeksForGeeks)
After adding two lists ListSet(Java, Csharp, Scala, Article, GeeksForGeeks)
```

**从列表集中移除元素:**我们可以使用–运算符移除列表集中的元素。下面是移除列表集中元素的示例。

```scala
// Scala program to Remove element from the ListSet
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        println("Initializing an immutable ListSet ")

        // Creating ListSet
        val listSet1: ListSet[String] = ListSet("GeeksForGeeks",
                                                "Article", "Scala")
        println(s"Elements of listSet1 = $listSet1")

        println("Remove element from the ListSet ")
        val listSet2: ListSet[String] = listSet1 - ("Article")
        println(s"After removing element from listset = $listSet2")

    } 
} 
```

**输出:**

```scala
Initializing an immutable ListSet 
Elements of listSet1 = ListSet(Scala, Article, GeeksForGeeks)
Remove element from the ListSet 
After removing element from listset = ListSet(Scala, GeeksForGeeks)
```

**初始化一个空的列表集:**

```scala
// Scala program to print empty ListSet
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating an empty ListSet
        println("Initialize an empty ListSet")
        val emptyListSet: ListSet[String] = ListSet.empty[String]
        println(s"String type empty ListSet = $emptyListSet")

    } 
} 
```

**输出:**

```scala
Initialize an empty ListSet
String type empty ListSet = ListSet()
```

**注意:**我们可以通过应用函数`**ListSet.empty**`或者调用构造函数来创建空的列表集。