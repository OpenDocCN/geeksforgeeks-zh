# Scala Stack:`:\()`方法示例

> 原文：[https://www.geeksforgeeks.org/scala-stack-method-with-example/](https://www.geeksforgeeks.org/scala-stack-method-with-example/)

在 Scala 中，`scala.collection.mutable` 包实现了堆栈数据结构。`:\` 方法对起始值和该可遍历或迭代器的所有元素应用二进制运算符，从右向左。

### 方法定义
`def :\[B](z: B)(op: (A, B) => B): B`

### 返回
在这个可遍历或迭代器的连续元素之间插入运算的结果。

## 示例#1

```scala
// Scala program of mutable stack :\() 
// method

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{

    // Main method 
    def main(args: Array[String]) 
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

```

## 例 2

```scala
// Scala program of mutable stack :\() method

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{

    // Main method 
    def main(args: Array[String]) 
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

```