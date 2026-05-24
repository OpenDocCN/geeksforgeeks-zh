# Java中LinkedBlockingDeque的`element()`方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-element-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-element-method-in-java/)

`LinkedBlockingDeque`的`element()`方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回由这个deque表示的队列头。

**语法：**

```java
public void element()
```

**参数：** 此方法不接受任何参数。

**返回：** 这个方法返回这个deque所代表的队列头。

下面的程序说明了`LinkedBlockingDeque`的`element()`方法：

## 程序1

```java
// Java Program Demonstrate element()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(10);
        LBD.add(20);
        LBD.add(30);
        LBD.add(40);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("Linked Blocking Deque front element: " +
                           LBD.element());
    }
}
```

**输出：**

```java
Linked Blocking Deque: [10, 20, 30, 40]
Linked Blocking Deque front element: 10
```

## 程序2

```java
// Java Program Demonstrate element()
// method of LinkedBlockingDeque
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("ab");
        LBD.add("cd");
        LBD.add("fg");
        LBD.add("xz");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("Linked Blocking Deque front element: " +
                           LBD.element());
    }
}
```

**输出：**

```java
Linked Blocking Deque: [ab, cd, fg, xz]
Linked Blocking Deque front element: ab
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#element()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#element())