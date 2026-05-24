# Java中LinkedBlockingDeque的toString()方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-tostring-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-tostring-method-in-java/)

`toString()`方法将`LinkedBlockingDeque`返回该集合的字符串表示形式。字符串表示由集合元素的列表组成，这些元素按照迭代器返回的顺序排列，用方括号括起来（`"[]"`）。相邻的元素由字符`", "`（逗号和空格）分隔。元素被转换为字符串，如`String.valueOf(Object)`。

## 语法
```java
public String toString()
```

## 参数
此方法不接受任何参数。

## 返回
该方法返回该集合的字符串表示形式。

以下程序说明了`LinkedBlockingDeque`的`toString()`方法：

## 程序1
```java
// Java Program Demonstrate toString()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("LBD in string " + LBD.toString());
    }
}
```

## 输出
```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
LBD in string [7855642, 35658786, 5278367, 74381793]
```

## 程序2
```java
// Java Program Demonstrate toString()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("geeks");
        LBD.add("sudo");
        LBD.add("gate");
        LBD.add("gopal");

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("LBD in string " + LBD.toString());
    }
}
```

## 输出
```java
Linked Blocking Deque: [geeks, sudo, gate, gopal]
LBD in string [geeks, sudo, gate, gopal]
```

## 参考
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#toString--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#toString--)