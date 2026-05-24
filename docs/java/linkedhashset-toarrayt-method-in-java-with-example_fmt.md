# 用示例：链接Java中的数组(T[])方法

> 原文：[https://www.geeksforgeeks.org/linkedhashset-toarrayt-method-in-java-with-example/](https://www.geeksforgeeks.org/linkedhashset-toarrayt-method-in-java-with-example/)

Java中`LinkedHashSet`类的`toArray(T[])`方法用于形成一个与`LinkedHashSet`相同元素的数组。它以正确的顺序返回一个数组，该数组包含这个`LinkedHashSet`中的所有元素；返回数组的运行时类型是指定数组的运行时类型。如果`LinkedHashSet`适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此`LinkedHashSet`的大小分配一个新数组。
如果`LinkedHashSet`适合有空余空间的指定数组（即数组中的元素比`LinkedHashSet`多），数组中紧接`LinkedHashSet`末尾的元素被设置为`null`。（只有当调用者知道`LinkedHashSet`不包含任何`null`元素时，这在确定`LinkedHashSet`的长度时才有用。）

## 语法

```java
public <T> T[] toArray(T[] a)
```

## 参数

该方法接受一个参数`arr[]`，如果足够大，则该参数是要存储`LinkedHashSet`元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

## 返回值

该方法返回一个数组，该数组包含类似于`LinkedHashSet`的元素。

## 异常

该方法可能会引发两种类型的异常：

*   `ArrayStoreException`：当提到的数组属于不同类型，无法与`LinkedHashSet`中提到的元素进行比较时。
*   `NullPointerException`：如果数组为`null`，那么抛出这个异常。

下面的程序说明了`LinkedHashSet.toArray(arr[])`方法的工作原理。

### 程序1：当数组的大小等于LinkedHashSet时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String>
            set = new LinkedHashSet<String>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = set.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The LinkedHashSet: [Welcome, To, Geeks, For]
The arr[] is:
Welcome
To
Geeks
For
null
```

### 程序2：当数组小于LinkedHashSet的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String>
            set = new LinkedHashSet<String>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = set.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The LinkedHashSet: [Welcome, To, Geeks, For]
The arr[] is:
Welcome
To
Geeks
For
```

### 程序3：当数组大于LinkedHashSet的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String>
            set = new LinkedHashSet<String>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = set.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The LinkedHashSet: [Welcome, To, Geeks, For]
The arr[] is:
Welcome
To
Geeks
For
null
null
null
null
null
null
```

### 程序4：演示NullPointerException

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String>
            set = new LinkedHashSet<String>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = set.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
The LinkedHashSet: [Welcome, To, Geeks, For]
Exception: java.lang.NullPointerException
```