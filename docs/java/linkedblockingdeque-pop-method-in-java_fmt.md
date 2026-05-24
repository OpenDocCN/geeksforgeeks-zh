# Java 中 LinkedBlockingDeque 的 pop() 方法

> 原文: [https://www.geeksforgeeks.org/linkedblockingdeque-pop-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-pop-method-in-java/)

`pop()` 方法从 `LinkedBlockingDeque` 所表示的栈中弹出一个元素。换句话说，它移除并返回此 deque 的第一个元素。如果此容器为空，它将返回 `null`。

## 语法
```java
public E pop()
```

## 参数
此方法不接受任何参数。

## 返回
此方法返回此 deque 前面的元素（即此 deque 所表示的栈的栈顶）。如果此 deque 为空，它会抛出一个 `NoSuchElementException`。

下面的程序说明了 `LinkedBlockingDeque` 的 `pop()` 方法：

## 程序 1
```java
// Java Program to demonstrate pop()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws NoSuchElementException
    {
        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793);

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints and deletes
        System.out.println("Front element in Deque: " + LBD.pop());

        // Deque after deletion of front element
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

## 输出
```java
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793
Linked Blocking Deque: [5278367, 35658786, 7855642]
```

## 程序 2
```java
// Java Program Demonstrate pop()
// method of LinkedBlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // empty deque
        LBD.clear();

        System.out.println("Front element in Deque: " + LBD.pop());
    }
}
```

## 输出
```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeFirst(LinkedBlockingDeque.java:453)
    at java.util.concurrent.LinkedBlockingDeque.pop(LinkedBlockingDeque.java:777)
    at GFG.main(GFG.java:27)
```

## 参考
[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#pop()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#pop())