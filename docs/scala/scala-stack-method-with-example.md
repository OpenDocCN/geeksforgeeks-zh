# Scala Stack:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-method-with-example/](https://www.geeksforgeeks.org/scala-stack-method-with-example/)

在 Scala 中，Scala . collection . mutatable 实现了堆栈数据结构。:\方法对起始值和该可遍历或迭代器的所有元素应用二进制运算符，从右向左。

> **方法定义–**def:\[B](z:B)(op:(A，B)？乙:乙
> 
> **返回–**在这个可遍历或迭代器的连续元素之间插入运算的结果。

**示例#1:**

```scala
// Scala program of mutable stack :\() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val st1 = Stack(1, 2, 3) 

        // Applying :\() method 
        val result1 = (st1 :\ 16 )(_+_)
        val result2 = (st1 :\ 16)(_-_)

        // Display output 
        print(result1)
        print("\n")
        print(result2)

    } 
} 
```

**Output:**

```scala
22
-14

```

**例 2:**

```scala
// Scala program of mutable stack :\() method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack 
        val q2 = List(11, 12, 13, 14, 15) 

        // Applying :\() method 
        val result = (q2 :\ 6)(_+_)

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
71

```