# Java 中的 Java.util.ArrayDeque 类|第 2 集

> 原文: [https://www.geeksforgeeks.org/java-util-arraydeque-class-java-set-2/](https://www.geeksforgeeks.org/java-util-arraydeque-class-java-set-2/)

[Java 中的 Java.util.ArrayDeque 类|集 1](https://www.geeksforgeeks.org/java-util-arraydeque-class-java/)

## util 的更多方法。ArrayDeque 类:

### 16. `offer(Element e)`: `java.util.ArrayDeque.offer(Element e)`
在 deque 的末尾插入 Element。
**语法:**
```java
public boolean offer(Element e)
Parameters : 
e - element to add
Return : 
true, if element is added else; false
```

### 17. `offerFirst(Element e)`: `java.util.ArrayDeque.offerFirst(Element e)`
在 deque 前面插入元素。
**语法:**
```java
public boolean offerFirst(Element e)
Parameters : 
e - element to add
Return : 
true, if element is added else; false
```

### 18. `offerLast(Element e)`: `java.util.ArrayDeque.offerLast(Element e)`
在 deque 的末尾插入元素。
**语法:**
```java
public boolean offerLast(Element e)
Parameters : 
e - element to add
Return : 
true, if element is added else; false
```

### 19. `peek()`: `java.util.ArrayDeque.peek()`
返回 head 元素，不移除。
**语法:**
```java
public E peek()
Parameters :

Return : 
head of deque or null if deque is empty.
```

### 20. `peekFirst()`: `java.util.ArrayDeque.peekFirst()`
返回第一个元素，不移除。
**语法:**
```java
public E peekFirst()
Parameters :

Return : 
first element of deque or null if deque is empty.
```

### 21. `peekLast()`: `java.util.ArrayDeque.peekLast()`
返回最后一个元素，不移除。
**语法:**
```java
public E peekLast()
Parameters :

Return : 
Last element of deque or null if deque is empty.
```

### 22. `poll()`: `java.util.ArrayDeque.poll()`
返回 head 元素并删除它。
**语法:**
```java
public E poll()
Parameters :

Return : 
head of deque or null if deque is empty.
```

### 23. `pollFirst()`: `java.util.ArrayDeque.pollFirst()`
返回第一个元素，同时删除它。
**语法:**
```java
public E pollFirst()
Parameters :

Return : 
first element of deque or null if deque is empty.
```

### 24. `pollLast()`: `java.util.ArrayDeque.pollLast()`
返回最后一个元素，并删除它。
**语法:**
```java
public E pollLast()
Parameters :

Return : 
last element of deque or null if deque is empty.
```

### 25. `pop()`: `java.util.ArrayDeque.pop()`
弹出一个元素进行叠加，由 deque 表示。
**语法:**
```java
public E pop()
Parameters :

Return : 
element at front
```

### 26. `push(Element e)`: `java.util.ArrayDeque.push(Element e)`
将一个元素推到由 deque 表示的堆栈上。
**语法:**
```java
public void push(Element e)
Parameters :
e : element to be pushed
Return :
```

### 27. `remove()`: `java.util.ArrayDeque.remove()`
返回 head 元素，同时也删除它。
**语法:**
```java
public E remove()
Parameters :

Return : 
head of the deque
```

### 28. `removeFirst()`: `java.util.ArrayDeque.removeFirst()`
返回第一个元素，同时删除它。
**语法:**
```java
public E removeFirst()
Parameters :

Return : 
first element of the deque
```

### 29. `removeLast()`: `java.util.ArrayDeque.removeLast()`
返回最后一个元素，并将其删除。
**语法:**
```java
public E removeLast()
Parameters :

Return : 
last element of the deque
```

### 30. `removeFirstOccurrence(Obj)`: `java.util.ArrayDeque.removeFirstOccurrence(Obj)`
移除元素中第一次出现的元素。
**语法:**
```java
public boolean removeFirstOccurrence(Object obj)
Parameters :
obj : element to be removed
Return : 
true, if the element is removed; else False
```

### 31. `removeLastOccurrence(Obj)`: `java.util.ArrayDeque.removeLastOccurrence(Obj)`
移除元素中最后出现的元素。
**语法:**
```java
public boolean removeLastOccurrence(Object obj)
Parameters :
obj : element to be removed
Return : 
true, if the element is removed; else False
```

## Java 程序解释 util。ArrayDeque 类方法:

### Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code explaining the use of ArrayDeque class methods
// offer(), offerFirst(), offerLast(), peek(), peekFirst(), peekLast()
// poll(), peekFirst(), peekLast(), pop(), push()

import java.util.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Initializing an deque
        Deque<Integer> d = new ArrayDeque<Integer>(10);

        // add() method to insert
        d.add(2);
        d.add(4);

        // offer() : add element at end
        d.offer(100);
        d.offer(101);

        // offerFirst() : add element at start
        d.offerFirst(1111);
        d.offerFirst(3333);

        // offerLast() : add element at end
        d.offerLast(5000);
        d.offerLast(50001);

        for (Integer element : d)
        {
            System.out.println("Element : " + element);
        }

        // peek() method : to get head
        System.out.println("\nHead element : " + d.peek());

        // peekFirst() method : to get First element
        System.out.println("First element : " + d.peekFirst());

        // peekLast() method : to get Last element
        System.out.println("Last element : " + d.peekLast());

        // poll() method : to get head
        System.out.println("\nHead element poll : " + d.poll());

        // pollFirst() method : to get First element
        System.out.println("First element poll : " + d.pollFirst());

        // pollLast() method : to get Last element
        System.out.println("Last element poll : " + d.pollLast() + "\n");

        for (Integer element : d)
        {
            System.out.println("Element : " + element);
        }

        // pop() method :
        System.out.println("Pop element : " + d.pop());

        // push() method :
        d.push(11010101);
        d.push(121212121);
        d.push(131313131);

        // remove() method : to get head
        System.out.println("\nHead element remove : " + d.remove());

        // removeFirst() method : to get First element
        System.out.println("First element remove : " + d.removeFirst());

        // removeLast() method : to get Last element
        System.out.println("Last element remove : " + d.removeLast() + "\n");

        for (Integer element : d)
        {
            System.out.println("Element : " + element);
        }

    }
}
```

### 输出:

```java
Element : 3333
Element : 1111
Element : 2
Element : 4
Element : 100
Element : 101
Element : 5000
Element : 50001

Head element : 3333
First element : 3333
Last element : 50001

Head element poll : 3333
First element poll : 1111
Last element poll : 50001

Element : 2
Element : 4
Element : 100
Element : 101
Element : 5000
Pop element : 2

Head element remove : 131313131
First element remove : 121212121
Last element remove : 5000

Element : 11010101
Element : 4
Element : 100
Element : 101
```

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。