# Java中LinkedBlockingDeque的isEmpty()方法详解

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-isempty-method-in-java-with-example/](https://www.geeksforgeeks.org/linkedblockingdeque-isempty-method-in-java-with-example/)

Java中`LinkedBlockingDeque`的`isEmpty()`方法用来检查这个`LinkedBlockingDeque`是否为空。它返回一个布尔值，表示相同的内容。

## 语法

```java
public boolean isEmpty()
```

## 参数
此方法不接受参数。

## 返回值
该方法返回一个`boolean`值，表示链接锁定请求的这个实例是否为空。

以下示例说明了`LinkedBlockingDeque.isEmpty()`方法：

## 程序1

```java
// Java Program Demonstrate isEmpty()
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
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        System.out.println("Linked Blocking Deque: " + LBD);

        // using isEmpty() function
        System.out.println("Is Linked Blocking Deque empty: "
                           + LBD.isEmpty());
    }
}
```

**Output:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Is Linked Blocking Deque empty: false
```

## 程序2

```java
// Java Program Demonstrate isEmpty()
// method of LinkedBlockingDeque
// when the list contains characters

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        System.out.println("Linked Blocking Deque: " + LBD);

        // using isEmpty() function
        System.out.println("Is Linked Blocking Deque empty: "
                           + LBD.isEmpty());
    }
}
```

**Output:**

```java
Linked Blocking Deque: []
Is Linked Blocking Deque empty: true
```