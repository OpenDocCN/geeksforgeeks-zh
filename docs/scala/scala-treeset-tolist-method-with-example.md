# Scala TreeSet toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-to list-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-tolist-method-with-example/)

**toList()** 方法用于返回包含树集合所有元素的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个包含树集合所有元素的列表。

**示例#1:**

```scala
// Scala program of toList() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying toList method  
        val result = t1.toList

        // Display output 
        print("Elements in the list: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Elements in the list: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toList() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet("u", "a", "i", "o", "e")  

        // Print the TreeSet 
        println(t1) 

        // Applying toList method  
        val result = t1.toList

        // Display output 
        print("Elements in the list: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Elements in the list: a e i o u

```