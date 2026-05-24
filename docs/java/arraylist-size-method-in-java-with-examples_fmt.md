# Java 中的 ArrayList size() 方法示例

> 原文: [https://www.geeksforgeeks.org/ArrayList-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/ArrayList-size-method-in-Java-with-examples/)

`ArrayList`类的`size()`方法用于获取该列表中的元素数量。

## 语法

```java
public int size()
```

## 返回值

该方法返回该列表中元素个数。

以下是说明`size()`方法的示例。

### 示例 1

```java
// Java program to demonstrate
// size() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

// Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist = new ArrayList<Integer>();

// Populating arrlist1
            arrlist.add(1);
            arrlist.add(2);
            arrlist.add(3);
            arrlist.add(4);
            arrlist.add(5);

// print arrlist
            System.out.println("Before operation: "
                               + arrlist);

// getting total size of arrlist
            // using size() method
            int size = arrlist.size();

// print the size of arrlist
            System.out.println("Size of list = "
                               + size);
        }

catch (IndexOutOfBoundsException e) {

System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```java
Before operation: [1, 2, 3, 4, 5]
Size of list = 5
```

### 示例 2

```java
// Java program to demonstrate
// size() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

// Creating object of ArrayList<Integer>
            ArrayList<String>
                arrlist = new ArrayList<String>();

// Populating arrlist1
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");

// print arrlist
            System.out.println("Before operation: "
                               + arrlist);

// getting total size of arrlist
            // using size() method
            int size = arrlist.size();

// print the size of arrlist
            System.out.println("Size of list = "
                               + size);
        }

catch (IndexOutOfBoundsException e) {

System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```java
Before operation: [A, B, C]
Size of list = 3
```