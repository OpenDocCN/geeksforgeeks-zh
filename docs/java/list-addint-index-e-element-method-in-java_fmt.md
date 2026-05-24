# Java 中的 List add(int index, E element) 方法

> 原文: [https://www.geeksforgeeks.org/list-addint-index-e-element-method-in-java/](https://www.geeksforgeeks.org/list-addint-index-e-element-method-in-java/)

`List` 接口的 `add(int index, E element)` 方法用于在当前列表中给定的索引处插入指定的元素。

## 语法

```java
public void add(int index, E element)
```

## 参数

这个方法接受两个参数，如上面的语法所示:

*   `index`：此参数指定要插入给定元素的索引。
*   `element`：此参数指定要插入到列表中的元素。

## 返回值

函数的返回类型为 `void`，不返回任何内容。

## 异常

*   `UnsupportedOperationException` – 如果此列表不支持 `add()` 操作，则抛出此异常。
*   `ClassCastException` – 如果指定元素的类阻止其被添加到此列表，则抛出此异常。
*   `NullPointerException` – 如果指定元素为空且列表不允许空元素，则抛出此异常。
*   `IllegalArgumentException` – 如果此元素的某些属性阻止其被添加到此列表，则抛出此异常。

下面的程序说明了 `List.add(int index, E element)` 方法:

## 程序 1

```java
// Java code to illustrate add(int index, E elements)
import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {
        // create an empty list with an initial capacity
        List<String> list = new ArrayList<String>(5);

        // use add() method to initially
        // add elements in the list
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");

        // Add a new element at index 0
        list.add(0, "Hello");

        // prints all the elements available in list
        for (String str : list) {
            System.out.print(str + " ");
        }
    }
}
```

## 输出

```java
Hello Geeks For Geeks
```

## 程序 2

```java
// Java code to illustrate add(int index, E elements)
import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {
        // create an empty list with an initial capacity
        List<Integer> list = new ArrayList<Integer>(5);

        // use add() method to initially
        // add elements in the list
        list.add(10);
        list.add(20);
        list.add(30);

        // Add a new 25 at index 2
        list.add(2, 25);

        // prints all the elements available in list
        for (Integer num : list) {
            System.out.print(num + " ");
        }
    }
}
```

## 输出

```java
10 20 25 30
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/List.html#add(int, %20E)](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#add(int, %20E))