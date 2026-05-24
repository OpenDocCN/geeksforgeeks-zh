# Scala TreeSet forall()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-for all-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-forall-method-with-example/)

在 Scala `TreeSet class`中，forall()的**方法用于检查谓词是否对树集的所有元素都成立。**

> ****方法定义:**定义为 all(p: (A) = >布尔型:布尔型**
> 
> ****返回类型:**如果谓词对 TreeSet 的所有元素都成立，则返回 true，否则返回 false。**

****示例#1:****

```scala
// Scala program of forall() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying forall() method  
        val result = t1.forall(x => {x % 7 == 0})

        // Displays output 
        println("All the elements are divisible by 7: " + result)

    } 
} 
```

****Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
All the elements are divisible by 7: false

```** 

****例 2:****

```scala
// Scala program of forall() 
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
        val t1 = TreeSet(2, 4, 6, 8) 

        // Print the TreeSet
        println(t1) 

        // Applying forall() method  
        val result = t1.forall(x => {x % 2 == 0})

        // Displays output 
        println("All the elements are even: " + result)

    } 
} 
```

****Output:**

```scala
TreeSet(2, 4, 6, 8)
All the elements are even: true

```**