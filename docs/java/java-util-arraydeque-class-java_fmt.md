# Java 中的 Java.util.ArrayDeque 类|集合 1

> 原文: [https://www.geeksforgeeks.org/java-util-arraydeque-class-java/](https://www.geeksforgeeks.org/java-util-arraydeque-class-java/)

`java.util.ArrayDeque` 类描述了 `可调整大小的数组` 结构的实现，该结构实现了 `Deque` 接口。
`ArrayDeque` 不是线程安全的，可以根据需要成长。它们不是线程安全的，因此除非显式同步，否则不支持多线程并发访问。空元素在此结构中无效。大多数操作在恒定时间内运行，速度随着大小的增长而线性下降。

## 申报

```java
public class ArrayDeque
   extends AbstractCollection
   implements Deque, Cloneable, Serializable
```

## 数组类的方法:

### 1. `add(Element e)`
[`add(Element e)`](https://www.geeksforgeeks.org/arraydeque-add-method-in-java/) 在元素末尾插入特定元素。
**语法:**

```java
public boolean add(Element e)
Parameter
e : element to add
Return
true : if element is inserted, else no
```

### 2. `addFirst(Element e)`
[`addFirst(Element e)`](https://www.geeksforgeeks.org/arraydeque-addfirst-method-in-java/) 在 `deque` 的开头插入特定元素。
**语法:**

```java
public boolean addFirst(Element e)
Parameter
e : element to add at the start
Return
true : if element is inserted, else no
```

### 3. `addLast(Element e)`
[`addLast(Element e)`](https://www.geeksforgeeks.org/arraydeque-addlast-method-in-java/) 在 `deque` 的末尾插入特定元素。类似于 `add()` 方法。
**语法:**

```java
public boolean addLast(Element e)
Parameter
e : element to add at end
Return
true : if element is inserted, else no
```

### 4. `clear()`
[`clear()`](https://www.geeksforgeeks.org/arraydeque-clear-method-in-java/) 移除了所有的 `deque` 元素。
**语法:**

```java
public void clear()
Parameter

Return
```

### 5. `size()`
[`size()`](https://www.geeksforgeeks.org/arraydeque-size-method-in-java/) 返回 `deque` 中的元素个数。
**语法:**

```java
public int size()
Parameter

Return
no. of elements in deque.
```

### 6. `clone()`
[`clone()`](https://www.geeksforgeeks.org/arraydeque-clone-method-in-java/) 复制了 `deque`。
**语法:**

```java
public ArrayDeque clone()
Parameter

Return
copy of deque
```

### 7. `contains(Object obj)`
[`contains(Object obj)`](https://www.geeksforgeeks.org/arraydeque-contains-method-in-java/) 检查一个 `deque` 是否包含该元素。
**语法:**

```java
public boolean contains(Object obj)
Parameter
obj : object to be checked
Return
true, if element is present in the deque; else false
```

### 8. `iterator()`
[`iterator()`](https://www.geeksforgeeks.org/arraydeque-iterator-method-in-java/) 返回一个对 `deque` 的迭代器。
**语法:**

```java
public Iterator iterator()
Parameter

Return
iterator over the deque.
```

### 9. `descendingIterator()`
[`descendingIterator()`](https://www.geeksforgeeks.org/arraydeque-descendingiterator-method-in-java/) 返回一个逆序迭代器，该迭代器覆盖了 `deque`。
**语法:**

```java
public Iterator descendingIterator()
Parameter

Return
returns a reverse order iterator over the deque.
```

### 10. `element()`
[`element()`](https://www.geeksforgeeks.org/arraydeque-element-method-in-java/) 返回元素在 `deque` 的头部。
**语法:**

```java
public E element()
Parameter

Return
head element of the deque
```

### 11. `getFirst()`
[`getFirst()`](https://www.geeksforgeeks.org/arraydeque-getfirst-method-in-java/) 返回 `deque` 的第一个元素。
**语法:**

```java
public E getFirst()
Parameter

Return
head element of the deque
```

### 12. `getLast()`
[`getLast()`](https://www.geeksforgeeks.org/arraydeque-getlast-method-in-java/) 返回 `deque` 的最后一个元素。
**语法:**

```java
public E getLast()
Parameter

Return
last element of the deque
```

### 13. `isEmpty()`
[`isEmpty()`](https://www.geeksforgeeks.org/arraydeque-isempty-method-in-java/) 检查 `deque` 是否为空。
**语法:**

```java
public boolean isEmpty()
Parameter

Return
true if the deque is empty; else false
```

### 14. `toArray()`
[`toArray()`](https://www.geeksforgeeks.org/arraydeque-toarray-method-in-java/) 返回具有 `deque` 元素的数组。
**语法:**

```java
public Object[] toArray()
Parameter

Return
returns array having the elements of deque.
```

## 解释 ArrayDeque 类方法的 Java 程序

```java
// Java code explaining the use of ArrayDeque class methods
// add(), addFirst(), addLast(), clear(), size(), contains()
// descendingIterator(), element(), getFirst(), isEmpty(),
// toArray, Iterator(), getLast()

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
        d.add(6);
        d.add(8);
        d.add(2);
        for (Integer element : d)
        {
            System.out.println("Element : " + element);
        }

        System.out.println("Using clear() ");
        //clear() method
        d.clear();

        // addFirst() method to insert at start
        d.addFirst(10);
        d.addFirst(20);

        // addLast() method to insert at end
        d.addLast(24);
        d.addLast(14);

        System.out.println("Above elements are removed now \n");

        //size() of ArrayDeque
        System.out.println("Size of deque : " + d.size() + "\n");
        for (Integer element : d)
        {
            System.out.println("Element : " + element);
        }

        // contains() method
        System.out.println("\nIs 10 present in deque : " + d.contains(10));

        // Iterator() :
        System.out.println("\nElements of deque using Iterator :");
        for(Iterator itr = d.iterator(); itr.hasNext();)
        {
            System.out.println(itr.next());
        }

        // descendingIterator() : to reverse the deque order
        System.out.println("\nElements of deque in reverse order :");
        for(Iterator dItr = d.descendingIterator(); dItr.hasNext();)
        {
            System.out.println(dItr.next());
        }

        // element() method : to get Head element
        System.out.println("\nHead Element using element(): " + d.element());

        // getFirst() method : to get Head element
        System.out.println("Head Element using getFirst(): " + d.getFirst());

        // getLast() method : to get last element
        System.out.println("Last Element using getLast(): " + d.getLast());

        // isEmpty() method :
        System.out.println("\nChecks whether deque is empty : " + d.isEmpty());

        //toArray() method :
        Object[] arr = d.toArray();
        System.out.println("\nArray Size : " + arr.length);

        System.out.print("Array elements : ");
        for(int i=0; i<arr.length ; i++)
            System.out.print(" " + arr[i]);
    }
}
```

## 输出

```
Element : 2
Element : 4
Element : 6
Element : 8
Element : 2
Using clear() 
Above elements are removed now

Size of deque : 4

Element : 20
Element : 10
Element : 24
Element : 14

Is 10 present in deque : true

Elements of deque using Iterator :
20
10
24
14

Elements of deque in reverse order :
14
24
10
20

Head Element using element(): 20
Head Element using getFirst(): 20
Last Element using getLast(): 14

Checks whether deque is empty : false

Array Size : 4
Array elements :  20 10 24 14
```

[Java 中的 Java.util.ArrayDeque 类|第 2 集](https://www.geeksforgeeks.org/java-util-arraydeque-class-java-set-2/)

本文由 **Mohit Gupta_OMG** 供稿🙂。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。