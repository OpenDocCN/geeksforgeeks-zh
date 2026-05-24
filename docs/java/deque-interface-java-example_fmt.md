# Java 中的 Deque 接口，示例

> 原文：[https://www.geeksforgeeks.org/deque-interface-java-example/](https://www.geeksforgeeks.org/deque-interface-java-example/)

出现在 [`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 `Deque` 接口是 [`Queue`](https://www.geeksforgeeks.org/queue-interface-java/) 接口的一个子类型。Deque 与双端队列相关，该队列支持从数据结构的任一端添加或移除元素。它既可以用作[队列（先进先出）](https://www.geeksforgeeks.org/queue/)也可以用作[堆栈（后进先出）](https://www.geeksforgeeks.org/stack/)。Deque 是“双端队列”的首字母缩写。

![Queue-Deque-PriorityQueue-In-Java](img/60cee2c4d09185f472d67be6d39b42a1.png)

**声明：** `Deque` 接口声明为：

```java
public interface Deque extends Queue
```

**创建 Deque 对象**

由于 `Deque` 是[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，因此不能直接创建 `Deque` 类型的对象。我们总是需要一个实现这个接口的类来创建一个对象。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)之后，可以限制可以存储在 `Deque` 中的对象类型。这种类型安全的队列可以定义为：

```java
// Obj 是要存储在 Deque 中的对象类型
Deque<Obj> deque = new ArrayDeque<Obj>();
```

**Deque 示例：**

```java
// Java program to demonstrate the working
// of a Deque in Java

import java.util.*;

public class DequeExample {
    public static void main(String[] args)
    {
        Deque<String> deque
            = new LinkedList<String>();

        // We can add elements to the queue
        // in various ways

        // Add at the last
        deque.add("Element 1 (Tail)");

        // Add at the first
        deque.addFirst("Element 2 (Head)");

        // Add at the last
        deque.addLast("Element 3 (Tail)");

        // Add at the first
        deque.push("Element 4 (Head)");

        // Add at the last
        deque.offer("Element 5 (Tail)");

        // Add at the first
        deque.offerFirst("Element 6 (Head)");

        System.out.println(deque + "\n");

        // We can remove the first element
        // or the last element.
        deque.removeFirst();
        deque.removeLast();
        System.out.println("Deque after removing "
                           + "first and last: "
                           + deque);
    }
}
```

**Output:**

```
[Element 6 (Head), Element 4 (Head), Element 2 (Head), Element 1 (Tail), Element 3 (Tail), Element 5 (Tail)]

Deque after removing first and last: [Element 4 (Head), Element 2 (Head), Element 1 (Tail), Element 3 (Tail)]
```

## 使用 Deque 接口和 ArrayDeque 类的操作

让我们看看如何使用 `ArrayDeque` 类在 deque 上执行一些常用的操作。

### 1. 添加元素

为了在一个 `Deque` 中添加一个元素，我们可以使用 [`add()`](https://www.geeksforgeeks.org/deque-add-method-in-java/) 方法。队列和双端队列之间的区别在于，在双端队列中，可以从任何方向进行添加。因此，还有另外两种方法可用，分别为 [`addFirst()`](https://www.geeksforgeeks.org/deque-addfirst-method-in-java-with-examples/) 和 [`addLast()`](https://www.geeksforgeeks.org/deque-addlast-method-in-java/)，用于在两端添加元素。

```java
// Java program to demonstrate the
// addition of elements in deque

import java.util.*;
public class ArrayDequeDemo {
    public static void main(String[] args)
    {
        // Initializing a deque
        Deque<String> dq
            = new ArrayDeque<String>();

        // add() method to insert
        dq.add("For");
        dq.addFirst("Geeks");
        dq.addLast("Geeks");

        System.out.println(dq);
    }
}
```

**Output:**

```
[Geeks, For, Geeks]
```

### 2. 移除元素

要从元素列表中移除元素，有多种方法可用。由于我们还可以从两端移除，所以 `Deque` 接口为我们提供了 `removeFirst()` 和 `removeLast()` 方法。除此之外，这个接口还为我们提供了 `poll()`、`pop()`、`pollFirst()`、`pollLast()` 方法，其中 `pop()` 用于移除和返回队列的头部。但是，通常使用 `poll()`，因为它提供了与 `pop()` 相同的功能，并且在 `Deque` 为空时不会抛出异常。

```java
// Java program to demonstrate the
// removal of elements in deque

import java.util.*;
public class ArrayDequeDemo {
    public static void main(String[] args)
    {
        // Initializing a deque
        Deque<String> dq
            = new ArrayDeque<String>();

        // add() method to insert
        dq.add("For");
        dq.addFirst("Geeks");
        dq.addLast("Geeks");

        System.out.println(dq);

        System.out.println(dq.pop());

        System.out.println(dq.poll());

        System.out.println(dq.pollFirst());

        System.out.println(dq.pollLast());
    }
}
```

**Output:**

```
[Geeks, For, Geeks]
Geeks
For
Geeks
null
```

### 3. 通过 Deque 迭代

由于一个 `Deque` 可以从两个方向迭代，因此 `Deque` 接口的迭代器方法为我们提供了两种迭代方式。一个在前面，另一个在后面。

```java
// Java program to demonstrate the
// iteration of elements in deque

import java.util.*;
public class ArrayDequeDemo {
    public static void main(String[] args)
    {
        // Initializing a deque
        Deque<String> dq
            = new ArrayDeque<String>();

        // add() method to insert
        dq.add("For");
        dq.addFirst("Geeks");
        dq.addLast("Geeks");
        dq.add("is so good");

        for (Iterator itr = dq.iterator();
             itr.hasNext();) {
            System.out.print(itr.next() + " ");
        }

        System.out.println();

        for (Iterator itr = dq.descendingIterator();
             itr.hasNext();) {
            System.out.print(itr.next() + " ");
        }
    }
}
```

**Output:**

```
Geeks For Geeks is so good 
is so good Geeks For Geeks
```

**实现 `Deque` 接口的类是 `ArrayDeque`。**

**[`ArrayDeque`](https://www.geeksforgeeks.org/arraydeque-in-java/)：** 在集合框架中实现的 `ArrayDeque` 类为我们提供了一种应用可调整大小的数组的方法。这是一种特殊的数组，它不断增长，允许用户在队列的两端添加或删除元素。`ArrayDeque` 内部数据区没有容量限制，可以根据需要增长以支持使用。它们不是线程安全的，这意味着在没有外部同步的情况下，`ArrayDeque` 不支持多线程并发访问。`ArrayDeque` 类用作堆栈时可能比 `Stack` 更快。当用作队列时，`ArrayDeque` 类可能比 `LinkedList` 更快。让我们看看如何使用这个类创建一个队列对象。

```java
// Java program to demonstrate the
// creation of deque object using the
// ArrayDeque class in Java

import java.util.*;
public class ArrayDequeDemo {
    public static void main(String[] args)
    {
        // Initializing a deque
        Deque<Integer> de_que
            = new ArrayDeque<Integer>(10);

        // add() method to insert
        de_que.add(10);
        de_que.add(20);
        de_que.add(30);
        de_que.add(40);
        de_que.add(50);

        System.out.println(de_que);

        // clear() method
        de_que.clear();

        // addFirst() method to insert the
        // elements at the head
        de_que.addFirst(564);
        de_que.addFirst(291);

        // addLast() method to insert the
        // elements at the tail
        de_que.addLast(24);
        de_que.addLast(14);

        System.out.println(de_que);
    }
}
```

**Output:**

```
[10, 20, 30, 40, 50]
[291, 564, 24, 14]
```

## Deque 接口的方法

以下是 `Deque` 接口中的方法：

| 方法 | 描述 |
| --- | --- |
| `add()` | 此方法用于在队列尾部添加一个元素。如果 Deque 受到容量限制，并且没有空间可供插入，它将返回 `IllegalStateException`。函数在成功插入时返回 `true`。 |
| `addFirst()` | 此方法用于在队列的头部添加一个元素。如果 Deque 受到容量限制，并且没有空间可供插入，它将返回 `IllegalStateException`。函数在成功插入时返回 `true`。 |
| `addLast()` | 此方法用于在队列尾部添加一个元素。如果 Deque 受到容量限制，并且没有空间可供插入，它将返回 `IllegalStateException`。函数在成功插入时返回 `true`。 |
| `contains()` | 此方法用于检查队列是否包含给定的对象。 |
| `descendingIterator()` | 这个方法为 deque 返回一个迭代器。元素将按从最后(尾部)到第一(头部)的顺序返回。 |
| `element()` | 此方法用于检索而不是移除由这个 deque 表示的队列头。 |
| `getFirst()` | 此方法用于检索而不是移除此 deque 的第一个元素。 |
| `getLast()` | 此方法用于检索，而不是移除此 deque 的最后一个元素。 |
| `iterator()` | 这个方法为 deque 返回一个迭代器。元素将按从第一个(头)到最后一个(尾)的顺序返回。 |
| `offer()` | 此方法用于在队列尾部添加一个元素。此方法比 `add()` 方法更可取，因为此方法不会在容器容量已满时引发异常，因为它返回 `false`。 |
| `offerFirst()` | 此方法用于在队列的头部添加一个元素。这个方法比 `addFirst()` 方法更好，因为这个方法不会在容器容量满的时候抛出异常，因为它返回 `false`。 |
| `offerLast()` | 此方法用于在队列尾部添加一个元素。此方法比 `add()` 方法更可取，因为此方法不会在容器容量已满时引发异常，因为它返回 `false`。 |
| `peek()` | 此方法用于检索 deque 头部的元素，但不会从 deque 中移除元素。如果 deque 为空，则此方法返回 `null`。 |
| `peekFirst()` | 此方法用于检索 deque 头部的元素，但不会从 deque 中移除元素。如果 deque 为空，则此方法返回 `null`。 |
| `peekLast()` | 此方法用于检索 deque 尾部的元素，但不会从 deque 中移除该元素。如果 deque 为空，则此方法返回 `null`。 |
| `poll()` | 此方法用于检索和移除 deque 头部的元素。如果 deque 为空，则此方法返回 `null`。 |
| `pollFirst()` | 此方法用于检索和移除 deque 头部的元素。如果 deque 为空，则此方法返回 `null`。 |
| `pollLast()` | 此方法用于检索和移除 deque 尾部的元素。如果 deque 为空，则此方法返回 `null`。 |
| `pop()` | 此方法用于从头部移除元素并将其返回。 |
| `push()` | 此方法用于在队列的头部添加一个元素。 |
| `removeFirst()` | 此方法用于从队列头移除元素。 |
| `removeLast()` | 此方法用于从队列尾部移除元素。 |
| `size()` | 此方法用于查找并返回 deque 的大小。 |