# Scala Queue `product()` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-queue-product-method-with-example/](https://www.geeksforgeeks.org/scala-queue-product-method-with-example/)

`product()` 方法用于返回队列中所有元素的乘积。

**方法定义:** `def product: B`

**返回类型:** 返回队列所有元素的乘积。

## 示例 1

```scala
// Scala program of product() 
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
        val q1 = Queue(1, 2, 3, 4)

// Print the queue
        println(q1)

// Applying product method 
        val result = q1.product

// Display output
        print("Product of all the elements of the queue: " + result)

} 
} 
```

**输出:**

```scala
Queue(1, 2, 3, 4)
Product of all the elements of the queue: 24
```

## 示例 2

```scala
// Scala program of product() 
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
        val q1 = Queue(5, 2, 3, 7)

// Print the queue
        println(q1)

// Applying product method 
        val result = q1.product

// Display output
        print("5 * 2 * 3 * 7 = " + result)

} 
} 
```

**输出:**

```scala
Queue(5, 2, 3, 7)
5 * 2 * 3 * 7 = 210
```