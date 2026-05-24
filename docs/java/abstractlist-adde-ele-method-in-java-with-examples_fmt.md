# 用示例列出 Java 中的 add(ele)方法

> 原文：[https://www.geeksforgeeks.org/abstractlist-adde-ele-method-in-java-with-examples/](https://www.geeksforgeeks.org/abstractlist-adde-ele-method-in-java-with-examples/)

## 方法描述
Java 中 `AbstractList` 类的 `add(E ele)` 方法用于将指定的元素插入到当前列表的末尾。

## 语法
`public boolean add(E ele)`

其中 `E` 是此抽象列表集合维护的元素类型。

## 参数
该方法接受单个参数 `ele`，该元素代表要在该列表末尾插入的元素。

## 返回值
如果元素成功插入列表，函数返回布尔值 `true`，否则返回 `false`。

## 异常
*   `UnsupportedOperationException` – 如果此列表不支持 `add()` 操作，它将引发此异常。
*   `ClassCastException` – 如果指定元素的类阻止它被添加到此列表中，它将引发此异常。
*   `NullPointerException` – 如果指定的元素为空并且该列表不允许空元素，它将引发此异常。
*   `IllegalArgumentException` – 如果这个元素的某些属性阻止它被添加到这个列表中，它就会抛出这个异常。

## 示例
下面的程序说明了抽象添加方法：

### 程序 1
```java
// Java code to illustrate add(Object o)
import java.io.*;
import java.util.*;

public class AbstractListDemo {
    public static void main(String[] args)
    {
        // create an empty list with an initial capacity
        AbstractList<Integer> list = new ArrayList<Integer>(5);

        // use add() method to add elements in the list
        list.add(15);
        list.add(20);
        list.add(25);

        // prints all the elements available in list
        for (Integer number : list) {
            System.out.println("Number = " + number);
        }
    }
}
```

**Output:**
```java
Number = 15
Number = 20
Number = 25
```

### 程序 2
```java
// Java code to illustrate add(Object o)
import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {
        // create an empty list with an initial capacity
        AbstractList<String> list = new ArrayList<String>(5);

        // use add() method to add elements in the list
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");

        // prints all the elements available in list
        for (String str : list) {
            System.out.print(str + " ");
        }
    }
}
```

**Output:**
```java
Geeks For Geeks
```

## 参考
[https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html#add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html#add(E))