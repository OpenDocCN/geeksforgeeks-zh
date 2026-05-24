# 列表缓冲量表

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-list buffer/

列表是包含不可变数据的集合。列表代表 Scala 中链接的[列表。列表是不可变的，如果我们需要创建一个不断变化的列表，首选的方法是使用**列表缓冲区**。
Scala List 类拥有一个有序的、线性的项目列表。只有从后向前，才能有效地建立列表。当我们想要从前到后构建一个列表时， *ListBuffer* 对象很方便。它支持高效的前置和后置操作。](https://www.geeksforgeeks.org/scala-lists/)

创建完列表后，调用`toList` 方法。要将列表缓冲区转换为列表，所用时间将保持不变。要使用列表缓冲区，需要导入`**scala.collection.mutable.ListBuffer** class`，创建一个列表缓冲区实例。

**示例:**

```scala
var name = new ListBuffer[datatype]()  // empty buffer is created

var name = new ListBuffer("class", "gfg", "geeksforgeeks")
```

在上面的例子中，首先，在这里创建一个空缓冲区，数据类型表示数据类型，如整数、字符串。然后用字符串类型的三个元素创建了一个缓冲区。

可以在列表缓冲区上执行以下操作–

*   通过使用 **L += e** 我们可以在恒定时间内追加元素 e。
*   通过使用 **e +=: L** 我们可以在恒定时间内预先考虑元素 e。
*   **L.toList** 在恒定时间内，它返回一个包含列表缓冲区内容的列表。一旦将列表缓冲区更改为列表，我们就不应该使用它。

## 对列表缓冲区的操作

**创建列表缓冲区实例:**

```scala
// Scala program to create a ListBuffer 
// ListBuffer class is imported 
import scala.collection.mutable.ListBuffer

// Creating object 
object GfG 
{ 

    // Main Method 
    def main(args: Array[String]) 
    { 
        // Instance of ListBuffer is created 
        var name = ListBuffer[String]()  
        name += "GeeksForGeeks"
        name += "gfg"
        name += "Class"
        println(name) 
    } 
} 
```

**输出:**

```scala
ListBuffer(GeeksForGeeks, gfg, Class)
```

**从列表缓冲区访问元素:**

元素的访问与列表相同，`ListBuffer(i)`用于访问列表的 *i <sup>th</sup>* 索引元素。

```scala
// Scala program to access element of ListBuffer 
// ListBuffer class is imported 
import scala.collection.mutable.ListBuffer 

// Creating Object 
object GFG 
{ 

    // Main Method 
    def main(args: Array[String]) 
    { 
        // Instance of ListBuffer is created 
        var name = ListBuffer[String]() 
        name += "GeeksForGeeks"
        name += "gfg"
        name += "Class"

        // Accessing 1th index element of listBuffer 
        println(name(1)) 
    } 
} 
```

**输出:**

```scala
gfg
```

**在列表缓冲区中添加元素:**

> *   Add a single element
>     
>     ```scala
>     ListBuffer+=( element)
>     ```
>     
>     to the buffer
> *   Add two or more elements (method has varargs parameter)
>     
>     ```scala
>      ListBuffer+= (element1, element2, ..., elementN )
>     ```
>     
>     
> *   Append one or more elements (using varargs parameter)
>     
>     ```scala
>     ListBuffer.append( elem1, elem2, ... elemN)
>     ```

```scala
// Scala program to add element in ListBuffer 
// ListBuffer class is imported 
import scala.collection.mutable.ListBuffer 

// Creating Object 
object GFG 
{ 

    // Main Method 
    def main(args: Array[String]) 
    { 
        // Instance of ListBuffer is created 
        var name = ListBuffer[String]() 

        // Adding one element 
        name += "GeeksForGeeks"

        // Add two or more elements 
        name += ("gfg", "class") 

        // Adding one or more element using append method 
        name.append("Scala", "Article") 

        // Printing ListBuffer 
        println(name) 
    } 
} 
```

**输出:**

```scala
ListBuffer(GeeksForGeeks, gfg, class, Scala, Article)
```

**删除列表缓冲区元素:**

> *   Remove an element
>     
>     ```scala
>     ListBuffer-= (element)
>     ```
>     
>     
> *   Remove multiple elements
>     
>     ```scala
>     ListBuffer-= (elem1, elem2, ....., elemN)
>     ```

```scala
// Scala program to delete element from ListBuffer 
// ListBuffer class is imported 
import scala.collection.mutable.ListBuffer 

// Creating Object 
object GFG 
{ 

    // Main Method 
    def main(args: Array[String]) 
    { 
        // Instance of ListBuffer is created 
        var name = ListBuffer( "GeeksForGeeks", "gfg", 
                                "class", "Scala", 
                                "Article" ) 

        // Deletes one element 
        name -= "GeeksForGeeks"

        // Deletes two or more elements 
        name -= ("gfg", "class") 

        // Printing resultant ListBuffer 
        println(name) 
    } 
} 
```

**输出:**

```scala
ListBuffer(Scala, Article)
```

**使用`ListBuffer.remove()` :** 删除列表缓冲区元素

`remove()`方法用于根据一个元素在`ListBuffer`中的位置删除该元素，或者从起始位置开始删除一系列元素。

```scala
// Scala program for remove method, on ListBuffer 
// ListBuffer class is imported 
import scala.collection.mutable.ListBuffer 

// Creating Object 
object GFG 
{ 

    // Main Method 
    def main(args: Array[String]) 
    { 
        // Instance of ListBuffer is created 
        var name = ListBuffer( "GeeksForGeeks", 
                                "gfg", "class", 
                                "Scala", "Article" ) 

        // Removing 0th index element 
        name.remove(0) 

        // Printing resultant ListBuffer 
        println(name) 
        name.remove(1, 3) 

        // Printing resultant ListBuffer 
        println(name) 
    } 
} 
```

**输出:**

```scala
ListBuffer(gfg, class, Scala, Article)
ListBuffer(gfg)
```