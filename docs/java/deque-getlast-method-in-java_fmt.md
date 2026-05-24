# Java 中的 Deque getLast() 方法

> 原文: [https://www.geeksforgeeks.org/deque-getlast-method-in-java/](https://www.geeksforgeeks.org/deque-getlast-method-in-java/)

[`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 接口的 [`getLast()`](https://www.geeksforgeeks.org/deque-getlast-method-in-java/) 方法返回 Deque 的最后一个元素或尾部。它不会删除元素。当 Deque 为空时，它会引发异常。

## 语法

```java
E getLast()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回最后一个元素或 Deque 的尾部，但不删除它。

## 异常
当 Deque 为空时调用此方法，函数会抛出 [`NoSuchElementException`](https://docs.oracle.com/javase/8/docs/api/java/util/NoSuchElementException.html)。

下面的程序说明了 [`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 的 [`getLast()`](https://www.geeksforgeeks.org/deque-getlast-method-in-java/) 方法：

### 程序 1：使用 [`LinkedList`](https://www.geeksforgeeks.org/linked-list-in-java/)

```java
// Java Program Demonstrate getLast()
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
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793
```

### 程序 2：使用 [`ArrayDeque`](https://www.geeksforgeeks.org/array-deque-in-java/)

```java
// Java Program Demonstrate getLast()
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
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793
```

### 程序 3：使用 [`ConcurrentLinkedDeque`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html)

```java
// Java Program Demonstrate getLast()
// method of Deque
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793
```

### 程序 4：使用 [`LinkedBlockingDeque`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html)

```java
// Java Program Demonstrate getLast()
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
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793
```

### 程序 5：当 Deque 为空时

```java
// Java Program Demonstrate getLast()
// method of Deque when it is empty
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());

        DQ.clear();

        // Deque is empty now hence exception
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.LinkedList.getLast(LinkedList.java:257)
    at GFG.main(GFG.java:29)
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#getLast--](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#getLast--)