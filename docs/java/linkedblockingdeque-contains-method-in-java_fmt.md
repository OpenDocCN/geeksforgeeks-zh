# LinkedBlockingDeque 在 Java 中的 contains() 方法

> 原文: [https://www.geeksforgeeks.org/linkedblockingdeque-contains-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-contains-method-in-java/)

`contains(Object o)` 方法检查参数中传递的元素是否存在于容器中。如果元素存在于容器中，则返回 `true`，否则返回 `false`。

## 语法

```java
public boolean contains(Object o)
```

## 参数

该方法接受一个强制参数 `o`，其在容器中的存在将被检查。

## 返回值

如果元素存在，这个方法返回 `true`，否则返回 `false`。

下面的程序说明了 `contains()` 方法在 `LinkedBlockingDeque` 中的使用：

## 示例程序

### 程序 1

```java
// Java Program Demonstrate contains()
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

        // check for presence using function
        if (LBD.contains(10)) {
            System.out.println("Linked Blocking Deque contains 10");
        }
        else {
            System.out.println("Linked Blocking Deque does not contain 10");
        }
    }
}
```

**输出:**

```java
Linked Blocking Deque: [10, 20, 30, 40]
Linked Blocking Deque contains 10
```

### 程序 2

```java
// Java Program Demonstrate contains()
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

        // check for presence using function
        if (LBD.contains("go")) {
            System.out.println("Linked Blocking Deque contains 'go'");
        }
        else {
            System.out.println("Linked Blocking Deque does not contain 'go'");
        }
    }
}
```

**输出:**

```java
Linked Blocking Deque: [ab, cd, fg, xz]
Linked Blocking Deque does not contain 'go'
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#contains(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#contains(java.lang.Object))