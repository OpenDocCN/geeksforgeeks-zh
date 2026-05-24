# Java 中数组到数组列表的转换

> 原文：[https://www.geeksforgeeks.org/array-to-arraylist-conversion-in-java/](https://www.geeksforgeeks.org/array-to-arraylist-conversion-in-java/)

`数组`是元素的集合，可以是原始数据类型，也可以是对象。Java 中的数组本质上是静态的。`数组列表`则只能将元素存储为对象。与数组不同，Java 中的数组列表本质上是动态的。数组列表是存在于 [`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中的集合类，它实现了 [`java.util.List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口。

可以使用以下方法将数组转换为数组列表：

## 1. 使用 `ArrayList.add()` 方法手动将数组元素添加到 `ArrayList` 中

此方法涉及创建一个新的 `ArrayList`，并使用 `add()` 方法将给定数组的所有元素添加到新创建的 `ArrayList` 中。

```
Syntax: public void add(int index, E element)
```

**参数：** 该功能接受 2 个强制参数：
*   `index` – 要插入指定元素的索引。
*   `element` – 要插入的元素。

**返回：** 该方法不返回任何值。

**异常：** 如果索引超出范围，该方法将抛出 [`IndexOutOfBoundsException`](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/)。

示例：

```java
// Java program to illustrate conversion 
// of an array to an ArrayList

import java.util.Arrays;
import java.util.ArrayList;

class ArrayToArrayList {
    public static void func1(int arr[])
    {
        ArrayList<Integer> array_list = 
                new ArrayList<Integer>();

        // Using add() method to add elements in array_list
        for (int i = 0; i < arr.length; i++)
            array_list.add(new Integer(arr[i]));
        System.out.print(array_list);
    }

    public static void main(String[] args)
    {
        int array[] = { 1, 2, 3, 4, 5 };
        func1(array);
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5]
```

## 2. 使用 `java.utils.Arrays` 类的 `Arrays.asList()` 方法

此方法将数组转换为列表，然后将该列表作为参数传递，以使用列表值初始化一个新的 `ArrayList`。

```
Syntax: public static List asList(T[] a)
```

**参数：** 该方法接受一个强制参数 `T[] a`，其中 `a` 是支持列表的数组，`T` 是数组的类型。

**返回：** 方法返回指定数组的列表视图。

示例：

```java
// Java program to illustrate conversion
// of an array to an ArrayList

import java.util.Arrays;
import java.util.ArrayList;

class ArrayToArrayList {
    public static void func2(Integer arr[])
    {
        // Using Arrays.asList() method
        ArrayList<Integer> array_list = 
            new ArrayList<Integer>(Arrays.asList(arr));
        System.out.print(array_list);
    }

    public static void main(String[] args)
    {
        // Integer objects are used instead
        // of primitives for conversion to list
        Integer array[] = { new Integer(1),
                            new Integer(2),
                            new Integer(3),
                            new Integer(4),
                            new Integer(5) };
        func2(array);
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5]
```

## 3. 使用 `java.utils.Collections` 类的 `Collections.addAll()` 方法

此方法将要插入数组值的 `ArrayList` 作为第一个参数；将要使用的数组作为第二个参数。然后将数组的值复制到 `ArrayList` 中。

```
Syntax: public static boolean addAll(Collection c, T.. a)
```

**参数：** 该方法接受 2 个强制参数：
*   `c` – 这是要插入元素的集合。
*   `a` – 要插入 `c` 的 `T` 型数组。

**返回：** 如果集合因调用而改变，则方法返回 `true`，否则返回 `false`。

**异常：** 方法抛出：
*   `UnsupportedOperationException`。
*   如果指定的集合为空，则抛出 `NullPointerException`。
*   `IllegalArgumentException` – 如果数组中某个值的某个方面阻止它被添加到 `c`。

示例：

```java
// Java program to illustrate conversion 
// of an array to an ArrayList

import java.util.Collections;
import java.util.ArrayList;

class ArrayToArrayList {
    public static void func3(String arr[])
    {
        ArrayList<String> array_list = new ArrayList<String>();

        // Using Collections.addAll() method
        Collections.addAll(array_list, arr);
        System.out.print(array_list);
    }

    public static void main(String[] args)
    {
        String array[] = { "ABC", "DEF", "GHI", "JKL" };
        func3(array);
    }
}
```

**Output:**

```java
[ABC, DEF, GHI, JKL]
```

## 4. 使用 `java.utils.Arrays` 类的 `Arrays.stream()` 方法

此方法创建数组值的顺序流。然后借助 `collect()` 方法和流，将值复制到 `ArrayList` 中。

```
Syntax: public static IntStream stream(T[] a)
```

**参数：** 该方法接受一个强制参数 `a`，该参数是要转换成类型为 `T` 的流的数组。
**返回：** 该方法返回指定类型的数组流（这里是 `IntStream`）。

**解说：** `Arrays.stream(arr).collect()` 方法使用 `java.util.stream.Collectors` 类，借助 `toList()` 方法将流转换为列表。

**注意：** 此方法需要 **Java 8** 或更高版本。

示例：

```java
// Java program to illustrate conversion 
// of an array to an ArrayList

import java.util.Arrays;
import java.util.ArrayList;
import java.util.stream.Collectors;

class ArrayToArrayList {
    public static void func4(String arr[])
    {
        // Using Arrays.stream.collect() method.
        ArrayList<String> array_list = (ArrayList<String>)
                    Arrays.stream(arr)
                          .collect(Collectors.toList());
        System.out.print(array_list);
    }

    public static void main(String[] args)
    {
        String array[] = { "ABC", "DEF", "GHI", "JKL" };
        func4(array);
    }
}
```

**Output:**

```java
[ABC, DEF, GHI, JKL]
```

## 5. 使用 `java.utils.List` 接口的 `List.of(Elements)` 方法

此方法将数组作为参数，然后创建数组值的不可变列表。然后将此不可变列表作为参数传递以创建一个新的 `ArrayList`。

```
Syntax: static {T} List{T} of(a)
```

**参数：** 该方法接受一个强制参数 `a`，它是要转换的数组，`T` 表示列表的元素类型（可以省略）。
**返回：** 方法返回包含指定元素的列表。
**异常：** 如果数组为空，该方法抛出 `NullPointerException`。

**注意：** 此方法需要 **Java 9** 或更高版本。

示例：

```java
// Java program to illustrate conversion 
// of an array to an ArrayList

import java.util.List;
import java.util.Arrays;
import java.util.ArrayList;
import java.util.stream.Collectors;

class ArrayToArrayList {
    public static void func5(String arr[])
    {
        // Using List.of() method.
        ArrayList<String> array_list = 
        new ArrayList<String>(List.of(arr));
        System.out.print(array_list);
    }

    public static void main(String[] args)
    {
        String array[] = { "ABC", "DEF", "GHI", "JKL" };
        func5(array);
    }
}
```

**Output:**

```java
[ABC, DEF, GHI, JKL]
```

### 参考文献

*   [https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html)
*   [https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html)
*   [https://docs.oracle.com/javase/9/docs/api/java/util/List.html](https://docs.oracle.com/javase/9/docs/api/java/util/List.html)