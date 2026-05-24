# Scala 队列 `apply()` 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-queue-apply-method-with-example/](https://www.geeksforgeeks.org/scala-queue-apply-method-with-example/)

`apply()` 方法用于查找队列中任意给定索引处的元素。

**方法定义：** `def apply(idx: Int): A`

**返回类型：** 返回队列给定索引处的元素。

## 示例 #1

```scala
// Scala program of apply() 
// method

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    { 
        // Creating a queue 
        val q1 = Queue(10, 11, 12, 13, 14)

// Print the queue
        println(q1)

// Applying apply() method 
        val result = q1.apply(0)

// Display output
        print("Element at index 0 : " + result)

} 
} 
```

**输出：**

```scala
Queue(10, 11, 12, 13, 14)
Element at index 0 : 10
```

## 示例 #2

```scala
// Scala program of apply() 
// method

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    { 
        // Creating a queue 
        val q1 = Queue(10, 11, 12, 13, 14)

// Print the queue
        println(q1)

// Applying apply() method 
        val result = q1.apply(2)

// Display output
        print("Element at index 2 : " + result)

} 
} 
```

**输出：**

```scala
Queue(10, 11, 12, 13, 14)
Element at index 2 : 12
```