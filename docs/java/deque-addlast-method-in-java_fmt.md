# Java 中的 Deque addLast()方法

> 原文:[https://www.geeksforgeeks.org/deque-addlast-method-in-java/](https://www.geeksforgeeks.org/deque-addlast-method-in-java/)

[`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/)接口的`addLast(E e)`方法将参数中传递的元素插入到Deque的末尾，如果有空间的话。如果`Deque`容量受限，并且没有空间可供插入，它将抛出一个`IllegalStateException`。函数在成功插入时返回`true`。

## 语法

```java
boolean addLast(E e)
```

## 参数

此方法接受一个强制参数`e`，它是要插入到Deque末尾的元素。

## 返回

该方法在成功插入时返回`true`。

## 异常

函数抛出四个异常，描述如下：

*   `ClassCastException`：当要插入元素的类阻止其被添加到此容器时抛出。
*   `IllegalStateException`：当容器容量已满且尝试插入时抛出。
*   `IllegalArgumentException`：当元素的某些属性阻止其被添加到`Deque`时抛出。
*   `NullPointerException`：当要插入的元素为`null`，且`Deque`接口不允许`null`元素时抛出。

下面的程序说明了实现`Deque`接口的各种类对`addLast()`方法的实现：

## 程序一：借助`LinkedList`

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
```

## 程序二：在`LinkedBlockingDeque`的帮助下

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
```

## 程序三：借助`ArrayDeque`

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
```