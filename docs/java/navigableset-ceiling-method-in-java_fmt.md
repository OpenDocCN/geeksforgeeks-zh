# Java 中的 NavigableSet ceiling() 方法

> 原文: [https://www.geeksforgeeks.org/navigableset-ceiling-method-in-java/](https://www.geeksforgeeks.org/navigableset-ceiling-method-in-java/)

Java 中 [`NavigableSet` 接口](https://www.geeksforgeeks.org/navigableset-java-examples/)的 `ceiling()` 方法用于返回该集合中大于或等于给定元素的最小元素，如果没有这样的元素，则返回 `null`。

## 语法

```java
E ceiling(E ele)
```

其中，`E` 是此 `Set` 容器维护的元素类型。

## 参数

该方法接受一个参数 `ele`，该参数是指定的、此 `Set` 容器维护的元素类型的元素。

## 返回值

返回该集合中大于等于给定元素的最小元素，如果没有，则返回 `null`。

下面的程序说明了 Java 中的 `ceiling()` 方法：

### 程序 1：带整数元素的 NavigableSet

```java
// A Java program to demonstrate
// working of NavigableSet
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

        System.out.println("Least element greater than"
               + " or equal to 4 is: " + ns.ceiling(4));
    }
}
```

**输出:**

```java
Least element greater than or equal to 4 is: 4
```

### 程序 2：带字符串元素的 NavigableSet

```java
// A Java program to demonstrate
// working of NavigableSet
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

        System.out.println("Least element greater than"
              + " or equal to D is: " + ns.ceiling("D"));
    }
}
```

**输出:**

```java
Least element greater than or equal to D is: D
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#ceiling(E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#ceiling(E))