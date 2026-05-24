# Java 中的 AbstractSequentialList.size() 方法示例

> 原文：[https://www.geeksforgeeks.org/abstractsequentiallist-size-method-in-java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-size-method-in-java-with-example/)

`AbstractSequentialList` 的 `size()` 方法用于获取该列表实例的大小。它返回一个整数值，表示此 `AbstractSequentialList` 实例中的元素数量。

## 语法

```java
public int size()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个整数值，它是此 `AbstractSequentialList` 实例的大小。

## 示例

以下示例说明了 `AbstractSequentialList.size()` 方法：

### 示例 1

```java
// Java code to demonstrate the working of
// size() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<Integer> arr
            = new LinkedList<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Get the size
        // using size()
        System.out.println("Size: "
                           + arr.size());
    }
}
```

**输出：**

```java
AbstractSequentialList: [1, 2, 3, 4]
Size: 4
```

### 示例 2

```java
// Java code to demonstrate the working of
// size() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<String> arr
            = new LinkedList<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Get the size
        // using size()
        System.out.println("Size: "
                           + arr.size());
    }
}
```

**输出：**

```java
AbstractSequentialList: [Geeks, For, ForGeeks, GeeksForGeeks]
Size: 4
```