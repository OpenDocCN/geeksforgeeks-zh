# Scala 队列 `contains()` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-queue-contains-method-with-example/](https://www.geeksforgeeks.org/scala-queue-contains-method-with-example/)

`contains()` 方法用于测试队列中是否存在元素。

## 方法定义

> **方法定义:** `def contains[A1 >: A](elem: A1): Boolean`
>
> **返回类型:** 如果该元素存在于队列中，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of contains()
// method

// Import Queue
import scala.collection.mutable._

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a queue
        val q1 = Queue(10, 11, 12, 13, 14)

        // Print the queue
        println(q1)

        // Applying contains() method
        val result = q1.contains(12)

        // Display output
        print("Queue contains 12: " + result)

    }
}
```

**输出:**

```scala
Queue(10, 11, 12, 13, 14)
Queue contains 12: true
```

## 示例 #2

```scala
// Scala program of contains()
// method

// Import Queue
import scala.collection.mutable._

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a queue
        val q1 = Queue(10, 11, 12, 13, 14)

        // Print the queue
        println(q1)

        // Applying contains() method
        val result = q1.contains(20)

        // Display output
        print("Queue contains 20: " + result)

    }
}
```

**输出:**

```scala
Queue(10, 11, 12, 13, 14)
Queue contains 20: false
```