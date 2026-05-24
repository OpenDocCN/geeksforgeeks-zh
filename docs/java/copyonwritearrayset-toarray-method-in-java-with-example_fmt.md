# Java 中的 CopyOnWriteArraySet toArray() 方法示例

> 原文：[https://www.geeksforgeeks.org/copyonwritearrayset-toarray-method-in-java-with-example/](https://www.geeksforgeeks.org/copyonwritearrayset-toarray-method-in-java-with-example/)

## `toArray()`

`java.util.concurrent.CopyOnWriteArraySet.toArray()` 方法返回一个包含集合中所有元素的正确顺序（从第一个到最后一个）的数组。创建新数组时，返回的数组将是安全的（因此会分配新内存）。因此调用者可以自由修改数组。它充当了基于数组和基于集合的 API 之间的桥梁。

### 语法

```java
public Object[] toArray()
```

### 参数
不取任何参数。

### 返回值
返回包含集合中所有元素的数组。

以下示例说明了 `CopyOnWriteArraySet.toArray()` 方法：

### 示例 1

```java
// Java Program Demonstrate toArray()
// method of CopyOnWriteArraySet

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {
        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> set
            = new CopyOnWriteArraySet<Integer>();

        // Add numbers to end of CopyOnWriteArraySet
        set.add(7855642);
        set.add(35658786);
        set.add(5278367);
        set.add(74381793);

        System.out.println("CopyOnWriteArraySet: "
                           + set);

        Object[] a = set.toArray();
        System.out.println("Returned Array: "
                           + Arrays.toString(a));
    }
}
```

### 输出

```java
CopyOnWriteArraySet: [7855642, 35658786, 5278367, 74381793]
Returned Array: [7855642, 35658786, 5278367, 74381793]
```

## `toArray(T[] a)`

Java 中 `CopyOnWriteArraySet` 类的 `toArray(T[] a)` 方法用于形成一个包含与 `CopyOnWriteArraySet` 相同元素的数组。它以正确的顺序返回一个包含所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。如果 `CopyOnWriteArraySet` 适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和该 `CopyOnWriteArraySet` 的大小分配一个新数组。

如果 `CopyOnWriteArraySet` 适合有空余空间的指定数组（即数组中的元素比 `CopyOnWriteArraySet` 多），则紧接在 `CopyOnWriteArraySet` 末尾的数组中的元素被设置为 `null`。（只有当调用者知道 `CopyOnWriteArraySet` 不包含任何 `null` 元素时，这在确定 `CopyOnWriteArraySet` 的长度时才有用。）

### 语法

```java
public <T> T[] toArray(T[] a)
```

### 参数
该方法接受一个参数 `a`，如果足够大的话，该参数就是要存储 `CopyOnWriteArraySet` 元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

### 返回值
该方法返回一个数组，该数组包含类似于 `CopyOnWriteArraySet` 的元素。

### 异常
该方法可能会引发两种类型的异常：

*   `ArrayStoreException`：当提到的数组属于不同的类型，无法与 `CopyOnWriteArraySet` 中提到的元素进行比较时。
*   `NullPointerException`：如果数组为 `null`，那么抛出这个异常。

下面的程序说明了 `CopyOnWriteArraySet.toArray(T[] a)` 方法的工作原理。

### 程序 1：当数组的大小为 CopyOnWriteArraySet 时

```java
// Java code to illustrate toArray(T[] a)

import java.util.concurrent.*;
import java.util.*;

public class CopyOnWriteArraySetDemo {
    public static void main(String args[])
    {
        // Creating an empty CopyOnWriteArraySet
        CopyOnWriteArraySet<String> set
            = new CopyOnWriteArraySet<String>();

        // Use add() method to add
        // elements into the CopyOnWriteArraySet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the CopyOnWriteArraySet
        System.out.println("The CopyOnWriteArraySet: "
                           + set);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = set.toArray(arr);

        // Displaying arr
        System.out.println("Returned Array: "
                           + Arrays.toString(arr));
    }
}
```

### 输出

```java
The CopyOnWriteArraySet: [Welcome, To, Geeks, For, Geeks]
Returned Array: [Welcome, To, Geeks, For, Geeks]
```