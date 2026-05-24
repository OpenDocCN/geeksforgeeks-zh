# Scala TreeSet copyToArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-copy to array-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-copytoarray-method-with-example/)

在 Scala `TreeSet class`中， **copyToArray()** 方法用于将树集的元素复制到数组中。

> **方法定义:**def copy to Array【B】T2:【A】(xs:Array【B】，start: Int，len: Int): Int
> 
> **参数:**
> **xs:** 表示复制元素的数组。
> **开始:**表示复制开始的索引。其默认值为 0。
> **len:** 表示要复制的元素数量。它的默认值是集合的长度。
> 
> **返回类型:**它将集合的元素返回到一个数组中。

**示例#1:**

```scala
// Scala program of copyToArray() 
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
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Creating an array 
        val arr = Array(0, 0, 0, 0, 0)

        // Applying copyToArray() method  
        t1.copyToArray(arr)

        // Displays output 
        println("Elements in the array: ")

        for(elem <- arr)  
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Elements in the array: 
1 2 3 4 5

```

**例 2:**

```scala
// Scala program of copyToArray() 
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
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Creating an array 
        val arr = Array(0, 0, 0, 0, 0)

        // Applying copyToArray() method  
        t1.copyToArray(arr, 1, 2)

        // Displays output 
        println("Elements in the array: ")

        for(elem <- arr)  
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Elements in the array: 
0 1 2 0 0

```