# Java 中的 `PriorityQueue` 类

> 原文: [https://www.geeksforgeeks.org/java-util-priorityqueue-class-java/](https://www.geeksforgeeks.org/java-util-priorityqueue-class-java/)

它是基于优先级堆的优先级队列。

*   这个类中的元素是按自然顺序排列的，或者取决于我们在构建时使用的构造函数。
*   它不允许空指针。
*   如果依赖于自然排序，则不允许插入不可比较的对象。

## 构造函数

*   `PriorityQueue()`: 创建一个具有默认初始容量(11)的 `PriorityQueue`，它根据元素的自然顺序对其进行排序。
*   `PriorityQueue(Collection c)`: 创建包含指定集合中元素的优先级队列。
*   `PriorityQueue(int initialCapacity)`: 创建一个具有指定初始容量的优先级队列，该队列根据元素的自然顺序对其进行排序。
*   `PriorityQueue(int initialCapacity, Comparator comparator)`: 创建具有指定初始容量的优先级队列，该队列根据指定的比较器对其元素进行排序。
*   `PriorityQueue(PriorityQueue c)`: 创建包含指定优先级队列中元素的优先级队列。
*   `PriorityQueue(SortedSet c)`: 创建包含指定排序集中元素的优先级队列。

## 声明

```java
public class PriorityQueue
   extends AbstractQueue
   implements Serializable
```

## 方法

### 1. `add(E e)`

将元素插入优先级队列。

**语法:**

```java
public boolean add(E e)
```

**参数:**
`element` : 我们需要添加的元素。

**返回:**
调用返回 `true`。

**异常:**
`ClassCastException`
`NullPointerException`

### 2. `comparator()`

`PriorityQueue.comparator()` 对队列中的元素进行排序。

**语法:**

```java
public Comparator comparator()
```

**参数:**
-------

**返回:**
对队列进行排序的比较器，如果它是自然排序的则返回 `null`。

**异常:**
----------

### 3. `contains(Object obj)`

`PriorityQueue.contains(obj)` 如果优先级队列包含元素 `obj`，则返回 `true`。

**语法:**

```java
public boolean contains(Object obj)
```

**参数:**
`obj` : 要检查的对象

**返回:**
`true` - 如果对象存在，否则返回 `false`。

**异常:**

### 4. `iterator()`

`PriorityQueue.iterator()` 迭代队列元素。

**语法:**

```java
public Iterator iterator()
```

**参数:**
-------

**返回:**
返回一个在队列元素上迭代的迭代器。

**异常:**
--------

### 5. `offer(E element)`

`PriorityQueue.offer()` 需要在给定的优先级队列中插入特定的元素。

**语法:**

```java
public boolean offer(E element)
```

**参数:**
`element` : 要输入的特定元素。

**返回:**
调用返回 `true`。

**异常:**
`ClassCastException`
`NullPointerException`

### 6. `peek()`

`PriorityQueue.peek()` 标识队列的头元素。

**语法:**

```java
public E peek()
```

**参数:**
-------

**返回:**
如果头存在则调用，否则返回 `null`。

**异常:**
------

### 7. `poll()`

`PriorityQueue.poll()` 识别头部，然后将其移除。

**语法:**

```java
public E poll()
```

**参数:**
---

**返回:**
如果头存在则调用，否则返回 `null`。

**异常:**
------

### 8. `remove(Object obj)`

从队列中移除特定对象。

**语法:**

```java
public boolean remove(Object obj)
```

**参数:**
`obj` : 要移除的对象

**返回:**
`true` - 如果 `obj` 被移除。

**异常:**
------

### 9. `size()`

`PriorityQueue.size()` 返回优先级队列中元素的大小。

**语法:**

```java
public int size()
```

**参数:**
----

**返回:**
元素数量。

**异常:**
---------

### 10. `toArray()`

`PriorityQueue.toArray()` 返回一个包含 `PriorityQueue` 元素的数组。

**语法:**

```java
public Object[] toArray()
```

**参数:**
------

**返回:**
返回一个包含 `PriorityQueue` 所有元素的数组。

**异常:**
--------

### 11. `toArray(T[] array)`

`PriorityQueue.toArray(T[] a)` 返回具有优先级队列元素的数组。

**语法:**

```java
public T[] toArray(T[] array)
```

**参数:**
`array` : 要排序到的数组。

**返回:**
调用返回一个包含数组所有元素的数组。

**异常:**
`ArrayStoreException`
`NullPointerException`

### 12. `clear()`

`PriorityQueue.clear()` 清除 `PriorityQueue` 的所有元素。

**语法:**

```java
public void clear()
```

**参数:**
---

**返回:**
------

**异常:**
------

## 示例代码

```java
// Java Program illustrating the methods
// of java.util.PriorityQueue class

// add(), comparator(), contains(), iterator(), offer()
// peek(), poll(), toArray(), size(), toArray(T[] g1),
// remove(), clear()

import java.util.*;

public class NewClass
{
    public static void main(String[] args)
    {
        // Creating a Priority Queue :
        PriorityQueue<Integer> geek = new PriorityQueue<Integer>();

        for(int i=2; i<=20; i=i+2)
        {
            // Use of add() :
            geek.add(new Integer(i));
        }

        System.out.println("geek PriorityQueue : " + geek);

        // Use of comparator()
        // No ordering is required here as it is naturally ordered.
        Comparator geek_comp = geek.comparator();
        System.out.println("geek PriorityQueue : " + geek_comp);

        // Use of contains()
        boolean check = geek.contains(6);
        System.out.println("Use of contains() : " + check);

        // Use of iterator()
        Iterator g_iterator = geek.iterator();

        System.out.print("Iterator values : ");
        while(g_iterator.hasNext())
        {
            System.out.print(g_iterator.next() + " ");
        }
        System.out.println("");

        // Use of offer()
        geek.offer(3050);
        System.out.println("geek PriorityQueue : " + geek);

        // Use of peek()
        System.out.println("Head of PriorityQueue via peek : " + geek.peek());

        //Use of poll()
        int h = geek.poll();
        System.out.println("\nHead of PriorityQueue via poll : " + h);
        System.out.println("geek PriorityQueue bcz of poll() : " + geek);

        // Use of remove()
        boolean r = geek.remove(8);
        System.out.println("\nCan remove : " + r);
        System.out.println("geek PriorityQueue bcz of remove() : " + geek);

        // use of size()
        System.out.println("\nSize of PriorityQueue : " + geek.size());

        // Use of toArray()
        Object[] g = geek.toArray();
        System.out.print("Array from PriorityQueue : ");

        for (int i = 0; i<g.length; i++)
        {
            System.out.print(g[i].toString() + " ");
        }

        System.out.println("\n");

        // Use of toArray(T[] g1) :
        Integer[] g2 = new Integer[5];
        Integer[] g1 = geek.toArray(g2);
        System.out.print("Array from PriorityQueue of size 5 : ");

        for (int i = 0; i<g1.length; i++)
        {
            System.out.print(g1[i].toString() + " ");
        }

        System.out.println("\n");

        // Use of clear()
        geek.clear();
        System.out.println("PriorityQueue after clear() : " + geek);
    }
}
```

## 输出

```
geek PriorityQueue : [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
geek PriorityQueue : null
Use of contains() : true
Iterator values : 2 4 6 8 10 12 14 16 18 20
geek PriorityQueue : [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 3050]
Head of PriorityQueue via peek : 2

Head of PriorityQueue via poll : 2
geek PriorityQueue bcz of poll() : [4, 8, 6, 16, 10, 12, 14, 3050, 18, 20]

Can remove : true
geek PriorityQueue bcz of remove() : [4, 10, 6, 16, 20, 12, 14, 3050, 18]

Size of PriorityQueue : 9
Array from PriorityQueue : 4 10 6 16 20 12 14 3050 18

Array from PriorityQueue of size 5 : 4 10 6 16 20 12 14 3050 18

PriorityQueue after clear() : []
```

本文由 **Mohit Gupta_OMG** 供稿🙂。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](http://www.write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。