# Java 中的 Deque offerLast()方法

> 原文: [https://www.geeksforgeeks.org/deque-offerlast-method-in-java/](https://www.geeksforgeeks.org/deque-offerlast-method-in-java/)

[`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 接口的 `offerLast(E e)` 方法在不违反容量限制的情况下，将指定元素插入双端队列的末尾。该方法优于 `add()` 方法，因为该方法在容器容量满时不会抛出异常，而是返回 `false`。

## 语法

```java
boolean offerLast(E e)
```

## 参数

此方法接受一个强制参数 `e`，它是要插入到双端队列末尾的元素。

## 返回

该方法在成功插入时返回 `true`，否则返回 `false`。

## 异常

该方法抛出三个异常，描述如下：

*   `ClassCastException`：当要插入元素的类阻止其被添加到此容器时抛出。
*   `IllegalArgumentException`：当元素的某些属性阻止其被添加到 `Deque` 时抛出。
*   `NullPointerException`：当要插入的元素为 `null`，且 `Deque` 接口不允许 `null` 元素时抛出。

## 程序示例

下面的程序说明了 `Deque` 的 `offerLast()` 方法：

### 程序 1：借助 `LinkedList`

```java
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]
```

### 程序 2：借助 `ArrayDeque`

```java
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]
```

### 程序 3：在 `ConcurrentLinkedDeque` 的帮助下

```java
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]
```