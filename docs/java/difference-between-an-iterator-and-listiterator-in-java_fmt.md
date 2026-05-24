# Java 中迭代器和列表迭代器的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-an-iterator-and-listiterator-in-java/](https://www.geeksforgeeks.org/difference-between-an-iterator-and-listiterator-in-java/)

## 迭代器

迭代器在 Java 的集合框架中使用，用于逐个检索元素。它可以应用于任何集合对象。通过使用迭代器，我们可以执行读取和移除操作。每当我们想要枚举所有 Collection 框架实现的接口中的元素时，比如 `Set`、`List`、`Queue`、`Deque`，以及映射接口的所有实现的类，都必须使用迭代器。迭代器是整个集合框架唯一可用的游标。

迭代器对象可以通过调用集合接口中的 `iterator()` 方法来创建。

```java
// Here "c" is any Collection object. itr is of
// type Iterator interface and refers to "c"
Iterator itr = c.iterator();
```

## 列表迭代器

仅适用于列表集合实现的类，如 `ArrayList`、`LinkedList` 等。它提供双向迭代。当我们想要枚举列表的元素时，必须使用列表迭代器。这个游标比迭代器有更多的功能（方法）。

列表迭代器对象可以通过调用列表接口中的 `listIterator()` 方法来创建。

```java
// Here "l" is any List object, ltr is of type
// ListIterator interface and refers to "l"
ListIterator ltr = l.listIterator();
```

## 迭代器和列表迭代器的区别

1.  `Iterator` 只能向前遍历集合中的元素，而 `ListIterator` 可以向前和向后遍历集合中的元素。

**示例:**

```java
import java.io.*;
import java.util.*;

class IteratorDemo1 {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();

        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        // Iterator
        Iterator itr = list.iterator();

        System.out.println("Iterator:");
        System.out.println("Forward traversal: ");

        while (itr.hasNext())
            System.out.print(itr.next() + " ");

        System.out.println();

        // ListIterator
        ListIterator i = list.listIterator();

        System.out.println("ListIterator:");
        System.out.println("Forward Traversal : ");

        while (i.hasNext())
            System.out.print(i.next() + " ");

        System.out.println();

        System.out.println("Backward Traversal : ");

        while (i.hasPrevious())
            System.out.print(i.previous() + " ");

        System.out.println();
    }
}
```

**输出:**

```java
Iterator:
Forward traversal: 
1 2 3 4 5

ListIterator:
Forward Traversal : 
1 2 3 4 5 
Backward Traversal : 
5 4 3 2 1
```

2.  `ListIterator` 可以帮助替换元素，而 `Iterator` 不能。

**示例:**

```java
import java.util.ArrayList;
import java.util.ListIterator;

public class ListIteratorDemo2 {
    public static void main(String[] args) {
        ArrayList<Integer> aList = new ArrayList<Integer>();
        aList.add(1);
        aList.add(2);
        aList.add(3);
        aList.add(4);
        aList.add(5);

        System.out.println("Elements of ArrayList: ");
        for (Integer i : aList) {
            System.out.println(i);
        }
        ListIterator<Integer> l = aList.listIterator();
        l.next();
        l.set(80000);

        System.out.println("\nNow the ArrayList elements are: ");
        for (Integer i : aList) {
            System.out.println(i);
        }
    }
}
```

**输出:**

```java
Elements of ArrayList: 
1
2
3
4
5

Now the ArrayList elements are: 
80000
2
3
4
5
```

## 迭代器和列表迭代器区别表

| 迭代器 | 列表迭代器 |
| --- | --- |
| 只能向前遍历集合中的元素。 | 可以向前和向后遍历集合中的元素。 |
| 帮助遍历 `Map`、`List` 和 `Set`。 | 只能遍历 `List`，不能遍历其他两个。 |
| 使用迭代器无法获得索引。 | 它有像 `nextIndex()` 和 `previousIndex()` 这样的方法，可以在遍历 `List` 时随时获取元素的索引。 |
| 无法修改或替换集合中存在的元素。 | 我们可以借助集合来修改或替换元素。 |
| 无法添加元素，并且它引发了 `ConcurrentModificationException`。 | 可以随时轻松地向集合中添加元素。 |
| 迭代器的某些方法是 `next()`、`remove()` 和 `hasNext()`。 | `ListIterator` 的某些方法是 `next()`、`previous()`、`hasNext()`、`hasPrevious()`、`add()`、`set()`。 |