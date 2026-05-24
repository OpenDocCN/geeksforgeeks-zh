# Scala 中的 HashMap

> 原文:[https://www.geeksforgeeks.org/hashmap-in-scala/](https://www.geeksforgeeks.org/hashmap-in-scala/)

散列表是 Scala 集合的一部分。它用于存储元素和返回地图。哈希映射是使用哈希表数据结构存储的键和值对的组合。它提供了[地图](https://www.geeksforgeeks.org/scala-map/)的基本实现。

**语法:**

```scala
var hashMapName = HashMap("key1"->"value1", "key2"->"value2", "key3"->"value3", ...) 
```

我们必须为 HashMap 导入 `scala.collection.mutable.HashMap`。

#### HashMap 执行的操作

**创建哈希表:**

下面是创建 HashMap 的示例。在下面的代码中，我们可以看到创建了一个空的 HashMap，然后用值创建了一个 HashMap。

```scala
// Scala program to create or print HashMap
import scala.collection.mutable.HashMap

// Creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating empty HashMap
        var hashMap = new HashMap()  

        // Creating HashMap with values
        var hashMap2 = HashMap("C"->"Csharp", "S"->"Scala", "J"->"Java")  

        // Printing HashMap
        println(hashMap)  
        println(hashMap2)  
    } 
} 
```

**输出:**

```scala
Map()
Map(S -> Scala, J -> Java, C -> Csharp)
```

**添加和访问元素:**

在下面的例子中，创建了一个散列表。还执行了添加元素和访问元素。

```scala
// Scala program to Adding and Accessing Elements HashMap
import scala.collection.mutable.HashMap

// Creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating HashMap
        var hashMap = HashMap("C"->"Csharp", "S"->"Scala", "J"->"Java")

        // Iterating elements
        hashMap.foreach 
        {  
            case (key, value) => println (key + " -> " + value)         
        }  

        // Accessing value by using key 
        println(hashMap("S"))  

        // Adding element
        var HashMap2 = hashMap + ("P"->"Perl")  
        HashMap2.foreach 
        {  
            case (key, value) => println (key + " -> " + value)  
        }  
    } 
} 
```

**输出:**

```scala
S -> Scala
J -> Java
C -> Csharp
Scala
S -> Scala
P -> Perl
J -> Java
C -> Csharp
```

**从散列表中移除元素:**
创建散列表，然后使用**–**符号移除元素。下面是从 HashMap 中移除元素的示例。

```scala
// Scala program to removing Element HashMap
import scala.collection.mutable.HashMap

// Creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating HashMap
        var hashMap = HashMap("C"->"Csharp", "S"->"Scala", "J"->"Java")

        // Iterating elements
        hashMap.foreach 
        { 
            case (key, value) => println (key + " -> " + value)         
        } 

        // Removing an element
        hashMap -= "C"

        println("After Removing")
        hashMap.foreach 
        { 
            case (key, value) => println (key + " -> " + value) 
        } 
    } 
} 
```

**输出:**

```scala
S -> Scala
J -> Java
C -> Csharp
After Removing
S -> Scala
J -> Java
```