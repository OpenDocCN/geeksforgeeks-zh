# Java 中的 CopyOnWriteArrayList add()方法

> 原文: [https://www.geeksforgeeks.org/copyonwritearraylist-add-method-in-java/](https://www.geeksforgeeks.org/copyonwritearraylist-add-method-in-java/)

`add(E e)` 方法将参数中传递的元素插入到列表的末尾或列表中的指定索引处。向列表中添加新元素时，该函数返回 `true`。

## 语法

```java
public boolean add(E e)
          or
public void add(int index, E element)
```

## 参数

该函数接受两种类型的参数，如下所述:

*   **Index:** 指定要添加元素的索引。此参数不是必需的。如果未传递此参数，则元素将添加到列表末尾。
*   **Element:** 指定要添加到列表中的元素。

## 返回值

该函数在列表中添加时返回 `true`。

以下程序说明了上述功能:

## 程序 1

```java
// Java Program to illustrate the CopyOnWriteArrayList
// add(element) method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

// Add elements
        ArrLis.add(2);
        ArrLis.add(3);
        ArrLis.add(4);
        ArrLis.add(7);

// print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

System.out.println("On adding 45 it returns "
                                     + ArrLis.add(45));
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [2, 3, 4, 7]
On adding 45 it returns true
```

## 程序 2

```java
// Java Program to illustrate the CopyOnWriteArrayList
// add(index, element) method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

// Add elements at 0th index
        ArrLis.add(0, 2);
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

// Add elements at 0th index
        ArrLis.add(0, 3);
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

// Add elements at 1st index
        ArrLis.add(1, 4);
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

// Add elements at 2nd index
        ArrLis.add(2, 7);
        System.out.println("CopyOnWriteArrayList: " + ArrLis);
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [2]
CopyOnWriteArrayList: [3, 2]
CopyOnWriteArrayList: [3, 4, 2]
CopyOnWriteArrayList: [3, 4, 7, 2]
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#add-E-)