# Java 中的 BlockingQueue remainingCapacity() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/blockingqueue-remainingcapacity-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-remainingcapacity-method-in-java-with-examples/)

[`BlockingQueue`](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/) 的 `remainingCapacity()` 方法返回可以添加到阻塞队列而不被阻塞的更多元素的数量。

返回的容量出现在三种情况下：

*   如果剩余容量为零，则无法再向阻塞队列添加任何元素。
*   如果阻塞队列的剩余容量等于队列的大小，则无法从队列中删除任何元素，因为此时队列为空。
*   在任何其他情况下，容量始终等于阻塞队列的初始容量与当前大小之间的差值。

## 语法

```java
public int remainingCapacity()
```

## 返回值

该方法返回阻塞队列的**剩余容量**。

## 注

`BlockingQueue` 的 `remainingCapacity()` 方法继承了 Java 中的 `Queue` 类。

下面的程序说明了 `BlockingQueue` 类的 `remainingCapacity()` 方法：

## 程序 1

```java
// Java Program Demonstrate remainingCapacity()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 7;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(
                capacityOfQueue);

        // Add element to BlockingQueue
        BQ.add("John");
        BQ.add("Tom");
        BQ.add("Clark");
        BQ.add("Kat");

        // find remaining Capacity  of BQ
        // using remainingCapacity() method
        int remainingCapacity
            = BQ.remainingCapacity();

        // print result
        System.out.println("Queue is " + BQ);

        // print head of the queue
        System.out.println("Remaining Capacity of Queue is "
                           + remainingCapacity);
    }
}
```

## 输出

```java
Queue is [John, Tom, Clark, Kat]
Remaining Capacity of Queue is 3
```

## 程序 2

```java
// Java Program Demonstrate remainingCapacity()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public void findPeek()
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 7;

        // create object of BlockingQueue
        BlockingQueue<Employee> BQ
            = new LinkedBlockingQueue<Employee>(
                capacityOfQueue);

        // Add element to BlockingQueue
        Employee emp1
            = new Employee("Ravi", "Tester", "39000");
        Employee emp2
            = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to BQ
        BQ.add(emp1);
        BQ.add(emp2);

        // add element and find remaining capacity
        // follow same process again
        // until the queue becomes full
        while (BQ.size() != 7) {

            // adding emp2 again and again to queue
            System.out.println(
                "Adding employee is success "
                + BQ.offer(emp2));

            // find remaining capacity of BQ
            // using remainingCapacity() method
            int remain = BQ.remainingCapacity();

            // print remaining capacity  value
            System.out.println(
                "Remaining Capacity of list :"
                + remain);
        }
    }

    // create an Employee Object with name,
    // position and salary as an attribute
    public class Employee {

        public String name;
        public String position;
        public String salary;
        Employee(String name,
                 String position,
                 String salary)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
        }
        @Override
        public String toString()
        {
            return "Employee [name=" + name
                + ", position="
                + position + ", salary="
                + salary + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.findPeek();
    }
}
```

## 输出

```java
Adding employee is success true
Remaining Capacity of list :4
Adding employee is success true
Remaining Capacity of list :3
Adding employee is success true
Remaining Capacity of list :2
Adding employee is success true
Remaining Capacity of list :1
Adding employee is success true
Remaining Capacity of list :0
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#remainingCapacity()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#remainingCapacity())