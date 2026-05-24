# Java 中的 Deque element()方法

> 原文: [https://www.geeksforgeeks.org/deque-element-method-in-java/](https://www.geeksforgeeks.org/deque-element-method-in-java/)

[`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 的 [`element()`](https://www.geeksforgeeks.org/deque-interface-java-example/) 方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回 Deque 的头。当 `Deque` 为空时，方法会引发异常。

**语法:**
```java
E element()
```

**参数:** 该方法不接受任何参数。
**返回:** 这个方法返回容器前面的元素或者 Deque 的头部。
**异常:** 当 `Deque` 为空，函数被调用时，函数抛出 [`NoSuchElementException`](https://www.geeksforgeeks.org/deque-interface-java-example/)。

下面的程序借助 [`LinkedList`](https://www.geeksforgeeks.org/linked-list-in-java/) 说明了 Deque 的 `element()` 方法:

### 程序 1:

```java
// Java Program Demonstrate element()
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
        System.out.println("Deque's head: " + DQ.element());
    }
}
```

**Output:**
```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 7855642
```

### 程序 2: 借助 [`ArrayDeque`](https://www.geeksforgeeks.org/deque-interface-java-example/)。

```java
// Java Program Demonstrate element()
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
        System.out.println("Deque's head: " + DQ.element());
    }
}
```

**Output:**
```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 7855642
```

### 程序 3: 在 [`ConcurrentLinkedDeque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 的帮助下。

```java
// Java Program Demonstrate element()
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
        System.out.println("Deque's head: " + DQ.element());
    }
}
```

**Output:**
```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 7855642
```

### 程序 4: 在 [`LinkedBlockingDeque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 的帮助下。

```java
// Java Program Demonstrate element()
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
        System.out.println("Deque's head: " + DQ.element());
    }
}
```

**Output:**
```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 7855642
```

### 程序 5: 演示异常情况。

```java
// Java Program Demonstrate element()
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
        System.out.println("Deque's head: " + DQ.element());

        DQ.clear();

        // Deque is empty now hence exception
        System.out.println("Deque's head: " + DQ.element());
    }
}
```

**输出:**
```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.LinkedList.getFirst(LinkedList.java:244)
    at java.util.LinkedList.element(LinkedList.java:663)
    at GFG.main(GFG.java:29)
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#element--](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#element--)