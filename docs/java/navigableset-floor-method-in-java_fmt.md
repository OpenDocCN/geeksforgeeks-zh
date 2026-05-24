# Java 中的 NavigableSet floor()方法

> 原文: [`https://www.geeksforgeeks.org/navigableset-floor-method-in-java/`](https://www.geeksforgeeks.org/navigableset-floor-method-in-java/)

Java 中 [`NavigableSet`](https://www.geeksforgeeks.org/navigableset-java-examples/) 接口的 [`floor()`](https://www.geeksforgeeks.org/navigableset-java-examples/) 方法用于返回该集合中小于或等于给定元素的最大元素，如果集合中不存在该元素，则返回 `null`。

## 语法

```java
E floor(E ele)
```

其中，`E` 是此 `Set` 容器维护的元素类型。

## 参数

该功能接受一个参数 `ele`，该参数是指该 `Set` 容器维护的元素类型。

## 返回值

返回该集合中小于等于给定元素的最大元素，如果没有该元素，则返回 `null`。

下面的程序说明了 Java 中的 [`floor()`](https://www.geeksforgeeks.org/navigableset-java-examples/) 方法：

### 程序 1：带整数元素的 NavigableSet

```java
// A Java program to demonstrate floor()
// method of NavigableSet
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

        System.out.println("Greatest element less than"
                + " or equal to 4 is: " + ns.floor(4));
    }
}
```

**输出:**

```java
Greatest element less than or equal to 4 is: 4
```

### 程序 2：带字符串元素的 NavigableSet

```java
// A Java program to floor()
// method of NavigableSet
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

        System.out.println("Greatest element less than"
                + " or equal to D is: " + ns.floor("D"));
    }
}
```

**输出:**

```java
Greatest element less than or equal to D is: D
```

## 参考

[`https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#floor(E)`](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#floor(E))