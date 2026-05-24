# Scala 中的列表图

> 原文:[https://www.geeksforgeeks.org/listmap-in-scala/](https://www.geeksforgeeks.org/listmap-in-scala/)

不可变映射通过使用基于列表的数据结构来实现。 [Scala 列表](https://www.geeksforgeeks.org/scala-lists/)类保存一个有序的线性项目列表。我们必须为 ListMap 导入 Scala . collection . mutatable . ListMap。ListMap 集合仅用于少量元素。
**语法:**

```scala
var listMapName = ListMap("k1"->"v1", "k2"->"v2", "k3"->"v3", ...) 
```

这里 **k** 是关键， **v** 是数值。

#### 列表映射执行的操作

**创建列表图:**
在下面的代码中，我们可以看到列表图是用值创建的。

## 斯卡拉

```scala
// Scala program to create or print ListMap
import scala.collection.immutable.ListMap

// Creating object
object Geeks
{

    // Main method
    def main(args: Array[String])
    {
        // Creating ListMap with values
        var listMap = ListMap("C"->"Csharp", "S"->"Scala", "J"->"Java")

        // Printing ListMap
        println(listMap)
    }
}
```

**输出:**

```scala
Map(C -> Csharp, S -> Scala, J -> Java)
```

**添加和访问元素:**
创建一个列表地图，添加元素和访问元素也执行。

## 斯卡拉

```scala
// Scala program to Adding and Accessing Elements ListMap
import scala.collection.mutable.ListMap

// Creating object
object Geeks
{

    // Main method
    def main(args: Array[String])
    {
        // Creating ListMap
        var listMap = ListMap("C"->"Csharp", "S"->"Scala", "J"->"Java")

        // Iterating elements
        listMap.foreach
        {
            case (key, value) => println (key + " -> " + value)        
        }

        // Accessing value by using key
        println(listMap("S"))

        // Adding element
        var ListMap2 = listMap + ("P"->"Perl")
        ListMap2.foreach
        {
            case (key, value) => println (key + " -> " + value)
        }
    }
}
```

**输出:**

```scala
J -> Java
C -> Csharp
S -> Scala
Scala
P -> Perl
C -> Csharp
J -> Java
S -> Scala
```

**从列表地图中移除元素:**
创建列表地图，然后使用–号执行移除元素。下面是从列表映射中移除元素的示例。

## 斯卡拉

```scala
// Scala program to removing Element from ListMap
import scala.collection.mutable.ListMap

// Creating object
object Geeks
{

    // Main method
    def main(args: Array[String])
    {
        // Creating ListMap
        var listMap = ListMap("C"->"Csharp", "S"->"Scala", "J"->"Java")

        // Iterating elements
        listMap.foreach
        {
            case (key, value) => println (key + " -> " + value)    
        }

        // Removing an element
        listMap -= "C"

        println("After Removing")
        listMap.foreach
        {
            case (key, value) => println (key + " -> " + value)
        }
    }
}
```

**输出:**

```scala
J -> Java
C -> Csharp
S -> Scala
After Removing
J -> Java
S -> Scala
```

**创建空列表地图:**
通过调用其构造函数或使用 ListMap.empty 方法创建空列表地图。

## 斯卡拉

```scala
// Scala program to Create an empty ListMap
import scala.collection.mutable.ListMap

// Creating object
object Geeks
{

    // Main method
    def main(args: Array[String])
    {
        // Creating an empty list map by calling constructor
        var ListMap1 = new ListMap()  

        // Creating an empty list map by using .empty method
        var ListMap2 = ListMap.empty

        // Printing empty ListMap
        println(emptyListMap1) 
        println(emptyListMap2) 
    }
}
```

**输出:**

```scala
Map()
Map()
```