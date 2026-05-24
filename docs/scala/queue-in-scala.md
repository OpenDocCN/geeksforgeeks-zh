# 斯卡拉排队

> 原文:[https://www.geeksforgeeks.org/queue-in-scala/](https://www.geeksforgeeks.org/queue-in-scala/)

一个**队列**是一个先进先出(FIFO)的数据结构。Scala 提供了不可变队列和可变队列。可变队列可以就地更新或扩展。这意味着人们可以改变、添加或删除队列元素作为副作用。相比之下，不可变队列永远不会改变。

在 Scala 中，队列被实现为一对列表。一个用于插入元素，第二个用于包含删除的元素。元素被添加到第一个列表中，并从第二个列表中移除。排队最基本的两个操作是*入队*和*出队*。

*   *入队*–在队列末尾添加一个元素。
*   *出列*–从队列的开头删除一个元素。

**队列中的方法:**

1.  **+=:** 此方法用于在队列末尾添加单个元素。
2.  **++=:** 这个方法用于在队列的末尾插入多个元素。
3.  **清除:**从队列中移除所有元素。
4.  **出列:**返回队列中的第一个元素
5.  **入队:**将所有元素添加到队列中。
6.  **等于:**检查两个队列在结构上是否相同。
7.  **front:** 返回队列中的第一个元素。
8.  **isEmpty:** 检查队列是否为空。

下面是演示这些操作的简单 Scala 程序:

**例 1:**

```scala
// Scala program for illustrating Queue

// Import Queue 
import scala.collection.mutable._

// Creating object
object GfG
{ 
    // Main method
    def main(args:Array[String])
    {
        // Initialize a queue
        var q1 = Queue(1, 2, 3, 4, 5)

        // Print the elements of queue
        print("Queue Elements: ")
        q1.foreach((element:Int) => print(element+" ")) 

        // Print the first element of the queue
        var firstElement = q1.front 
        println("\nFirst element in the queue: "+ firstElement) 

        // Enqueue 10 in the queue
        q1.enqueue(10) 

        // Print the elements of queue
        print("Queue Elements after enqueue: ") 
        q1.foreach((element:Int) => print(element+" "))

        // Dequeue first element from the queue
        var deq = q1.dequeue

        // Print the elements of queue
        print("\nQueue Elements after dequeue: ") 
        q1.foreach((element:Int) => print(element+" "))

        // Print the Dequeued element
        print("\nDequeued element: " + deq)

        // using isEmpty method
        println("\nQueue is empty: "+ q1.isEmpty)
    }
}
```

**Output:**

```scala
Queue Elements: 1 2 3 4 5 
First element in the queue: 1
Queue Elements after enqueue: 1 2 3 4 5 10 
Queue Elements after dequeue: 2 3 4 5 10 
Dequeued element: 1
Queue is empty: false

```

**例 2:**

```scala
// Scala program for illustrating Queue

// Import Queue 
import scala.collection.mutable._

// Creating object
object GfG
{ 
    // Main method
    def main(args:Array[String])
    {
        // Initialize a queue
        var fruits = Queue[String]()

        // Adding elements to the queue
        fruits.enqueue("apple")
        fruits.enqueue("banana")
        fruits.enqueue("mango")
        fruits.enqueue("guava")

        // Print the elements of queue
        print("Queue Elements: ")
        fruits.foreach((element:String) => print(element+" ")) 

        // Print the first element of the queue
        var firstElement = fruits.front 
        println("\nFirst element in the queue: "+ firstElement) 

        // Enqueue pineapple in the queue
        fruits.enqueue("pineapple") 

        // Print the elements of queue
        print("Queue Elements after enqueue: ") 
        fruits.foreach((element:String) => print(element+" "))

        // Dequeue first element from the queue
        var deq = fruits.dequeue

        // Print the elements of queue
        print("\nQueue Elements after dequeue: ") 
        fruits.foreach((element:String) => print(element+" "))

        // Print the Dequeued element
        print("\nDequeued element: " + deq)

        // Using clear method
        println("\nclear the queue: "+ fruits.clear)

        // Using isEmpty method
        println("\nqueue is empty: "+ fruits.isEmpty)

    }
}
```

**Output:**

```scala
Queue Elements: apple banana mango guava 
First element in the queue: apple
Queue Elements after enqueue: apple banana mango guava pineapple 
Queue Elements after dequeue: banana mango guava pineapple 
Dequeued element: apple
clear the queue: ()

queue is empty:true

```