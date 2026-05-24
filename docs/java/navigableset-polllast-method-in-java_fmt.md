# Java 中的 `NavigableSet` `pollLast()` 方法

> 原文：[https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/](https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/)

Java 中 `NavigableSet` 接口的 `pollLast()` 方法用于检索并移除最后一个（最高的）元素，如果该集合为空，则返回 `null`。

## 语法

```java
E pollLast()
```

其中，`E` 是此 `Set` 容器维护的元素类型。

## 参数

本方法不接受任何参数。

## 返回值

返回最后一个（最高的）元素，如果该集合为空，则返回 `null`。

## 程序示例

下面的程序说明了 Java 中的 `pollLast()` 方法：

### 程序 1：带整数元素的 `NavigableSet`

```java
// A Java program to demonstrate
// pollLast() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<Integer> ns = new TreeSet<>();
        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        System.out.println("Greatest(last) element removed is : "
                           + ns.pollLast());
    }
}
```

**输出：**

```java
Greatest(last) element removed is : 6
```

### 程序 2：带字符串元素的 `NavigableSet`

```java
// A Java program to demonstrate
// pollLast() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<String> ns = new TreeSet<>();
        ns.add("A");
        ns.add("B");
        ns.add("C");
        ns.add("D");
        ns.add("E");
        ns.add("F");
        ns.add("G");

        System.out.println("Greatest(last) element removed is : "
                           + ns.pollLast());
    }
}
```

**输出：**

```java
Greatest(last) element removed is : G
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#pollLast(E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#pollLast(E))