# Scala 队列 `copyToArray()` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-queue-copytoarray-method-with-example/](https://www.geeksforgeeks.org/scala-queue-copytoarray-method-with-example/)

`copyToArray()` 方法用于将队列的元素复制到数组中。

> **方法定义:** `def copyToArray[B >: A](xs: Array[B], start: Int, len: Int): Int`
>
> **参数:**
> `xs`: 表示复制元素的数组。
> `start`: 表示复制开始的索引。其默认值为 0。
> `len`: 表示要复制的元素数量。它的默认值是集合的长度。
>
> **返回类型:** 它将集合的元素返回到一个数组中。

## 示例#1:

```scala
// Scala program of copyToArray() 
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
        val q1 = Queue(1, 2, 3)

// Creating an array
        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

// Applying copyToArray method 
        q1.copyToArray(arr)

// Displays output 
        for(elem <- arr) 
        println(elem)

} 
} 
```

**Output:**

```scala

```

## 例 2:

```scala
// Scala program of copyToArray() 
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
        val q1 = Queue(1, 2, 3)

// Creating an array
        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

// Applying copyToArray method 
        q1.copyToArray(arr, 1, 2)

// Displays output 
        for(elem <- arr) 
        println(elem)

} 
} 
```

**Output:**

```scala

```