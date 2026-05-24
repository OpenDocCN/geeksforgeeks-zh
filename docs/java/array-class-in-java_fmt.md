# Java 中的数组类

> 原文: [https://www.geeksforgeeks.org/array-class-in-java/](https://www.geeksforgeeks.org/array-class-in-java/)

`java.util`包中的`Arrays`类是`Java`集合框架的一部分。这个类提供静态方法来动态创建和访问`Java`数组。它只包含静态方法和对象类的方法。这个类的方法可以由类名本身使用。

类层次结构如下：

```java
java.lang.Object
 ↳ java.util.Arrays
```

Geek，现在你一定想知道，当我们能够在数组上声明、初始化和计算操作时，为什么我们需要`java Arrays`类。这个问题的答案在这个类的方法中，我们将进一步讨论，因为实际上这些函数帮助程序员扩展数组的视野，例如，经常有[循环](https://www.geeksforgeeks.org/loops-in-java/)被用来在数组上执行一些任务，比如：

*   用特定值填充数组。
*   对数组进行排序。
*   在数组中搜索。
*   还有更多。

> 这里，`Arrays`类提供了几个静态方法，可以用来直接执行这些任务，而不需要使用循环，从而使我们的代码变得超级短和优化。

**语法：** 类声明

```java
public class Arrays
    extends Object
```

**语法：** 为了使用数组

```java
Arrays.<function name>;
```

## Java 数组类中的方法

[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)的`Arrays`类包含了几个静态方法，可以用来填充、排序、搜索等数组。现在让我们讨论一下这个类的方法，如下表所示：

| 方法 | 执行的操作 |
| --- | --- |
| `asList()` | 返回由指定数组支持的固定大小列表。 |
| `binarySearch()` | 使用二分查找算法搜索数组中的指定元素。 |
| `compare(array1, array2)` | 按字典顺序比较作为参数传递的两个数组。 |
| `compareUnsigned(array1, array2)` | 按字典顺序比较两个数组，不考虑符号。 |
| `copyOf(originalArray, newLength)` | 复制指定的数组，截断或填充默认值（如果需要），使副本具有指定的长度。 |
| `copyOfRange(originalArray, fromIndex, toIndex)` | 将指定数组的指定范围复制到新数组中。 |
| `deepEquals(object1, object2)` | 如果两个指定的数组深度相等，则返回`true`。 |
| `deepHashCode(object[] a)` | 根据指定数组的“深度内容”返回哈希码。 |
| `deepToString(object[] a)` | 返回指定数组“深度内容”的字符串表示形式。 |
| `equals(array1, array2)` | 检查两个数组是否相等。 |
| `fill(array, value)` | 将指定的填充值分配给数组的每个索引。 |
| `hashCode(originalArray)` | 返回此数组实例的整数`hashCode`。 |
| `mismatch(array1, array2)` | 查找并返回两个指定数组之间第一个不匹配元素的索引。 |
| `parallelPrefix(originalArray, fromIndex, endIndex, functionOperator)` | 使用指定的函数运算符在给定的数组范围内并行执行前缀计算。 |
| `parallelPrefix(originalArray, operator)` | 使用指定的函数运算符在整个数组上并行执行前缀计算。 |
| `parallelSetAll(originalArray, functionGenerator)` | 使用提供的生成器函数并行设置数组的所有元素。 |
| `setAll(originalArray, functionGenerator)` | 使用提供的生成器函数设置指定数组的所有元素。 |
| `sort(originalArray)` | 按升序对整个数组进行排序。 |
| `sort(originalArray, fromIndex, endIndex)` | 按升序对数组的指定范围进行排序。 |
| `sort(objectArray, comparator)` | 根据指定比较器总结的顺序对指定的对象数组进行排序。 |
| `sort(objectArray, fromIndex, endIndex, comparator)` | 根据指定比较器总结的顺序对指定对象数组的指定范围进行排序。 |
| `spliterator(originalArray)` | 返回覆盖所有指定数组的`Spliterator`。 |
| `spliterator(originalArray, fromIndex, endIndex)` | 返回覆盖指定数组指定范围的数组类型的`Spliterator`。 |
| `stream(originalArray)` | 返回以指定数组为源的顺序流。 |
| `toString(originalArray)` | 返回此数组内容的字符串表示形式。字符串表示形式由方括号（`[]`）括起来的数组元素列表组成。相邻元素由逗号和空格分隔。将函数元素转换为字符串。 |

## 实施

### 例 1：`asList()`方法

```java
// Java Program to Demonstrate Arrays Class
// Via asList() method

// Importing Arrays utility class
// from java.util package
import java.util.Arrays;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To convert the elements as List
        System.out.println("Integer Array as List: "
                           + Arrays.asList(intArr));
    }
}
```

**Output**

```java
Integer Array as List: [[I@2f4d3709]
```

### 例 2：`binarySearch()`方法

这些方法在二分查找算法的帮助下搜索数组中的指定元素。

```java
// Java Program to Demonstrate Arrays Class
// Via binarySearch() method

// Importing Arrays utility class
// from java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        Arrays.sort(intArr);

        int intKey = 22;

        // Print the key and corresponding index
        System.out.println(
            intKey + " found at index = "
            + Arrays.binarySearch(intArr, intKey));
    }
}
```

**Output**

```java
22 found at index = 3
```

### 示例 3：`binarySearch(array, fromIndex, toIndex, key, comparator)`方法

此方法使用二分查找算法在指定数组的范围内搜索指定对象。

```java
// Java program to demonstrate
// Arrays.binarySearch() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        Arrays.sort(intArr);

        int intKey = 22;

        System.out.println(
            intKey
            + " found at index = "
            + Arrays
                  .binarySearch(intArr, 1, 3, intKey));
    }
}
```

**Output**

```java
22 found at index = -4
```

### 示例 4：`compare(array1, array2)`方法

```java
// Java program to demonstrate
// Arrays.compare() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Array
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.compare(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: 1
```

### 示例 5：`compareUnsigned(array1, array2)`方法

```java
// Java program to demonstrate
// Arrays.compareUnsigned() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.compareUnsigned(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: 1
```

### 例 6：`copyOf(originalArray, newLength)`方法

```java
// Java program to demonstrate
// Arrays.copyOf() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To print the elements in one line
        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));

        System.out.println("\nNew Arrays by copyOf:\n");

        System.out.println("Integer Array: "
                           + Arrays.toString(
                                 Arrays.copyOf(intArr, 10)));
    }
}
```

**Output**

```java
Integer Array: [10, 20, 15, 22, 35]

New Arrays by copyOf:

Integer Array: [10, 20, 15, 22, 35, 0, 0, 0, 0, 0]
```

### 例 7：`copyOfRange(originalArray, fromIndex, endIndex)`方法

# Java Arrays 类常用方法示例

## 示例 8: `deepEquals(Object[] a1, Object[] a2)` 方法

```java
// Java program to demonstrate
// Arrays.deepEquals() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // Get the second Arrays
        int intArr1[][] = { { 10, 15, 22 } };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.deepEquals(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: false
```

## 示例 9: `deepHashCode(Object[] a)` 方法

```java
// Java program to demonstrate
// Arrays.deepHashCode() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // To get the dep hashCode of the arrays
        System.out.println("Integer Array: "
                           + Arrays.deepHashCode(intArr));
    }
}
```

**Output**

```java
Integer Array: 38475344
```

## 示例 10: `deepToString(Object[] a)` 方法

```java
// Java program to demonstrate
// Arrays.deepToString() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // To get the deep String of the arrays
        System.out.println("Integer Array: "
                           + Arrays.deepToString(intArr));
    }
}
```

**Output**

```java
Integer Array: [[10, 20, 15, 22, 35]]
```

## 示例 11: `equals(array1, array2)` 方法

```java
// Java program to demonstrate
// Arrays.equals() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.equals(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: false
```

## 示例 12: `fill(originalArray, fillValue)` 方法

```java
// Java program to demonstrate
// Arrays.fill() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        int intKey = 22;

        Arrays.fill(intArr, intKey);

        // To fill the arrays
        System.out.println("Integer Array on filling: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array on filling: [22, 22, 22, 22, 22]
```

## 示例 13: `hashCode(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.hashCode() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To get the hashCode of the arrays
        System.out.println("Integer Array: "
                           + Arrays.hashCode(intArr));
    }
}
```

**Output**

```java
Integer Array: 38475313
```

## 示例 14: `mismatch(array1, array2)` 方法

```java
// Java program to demonstrate
// Arrays.mismatch() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("The element mismatched at index: "
                           + Arrays.mismatch(intArr, intArr1));
    }
}
```

**Output**

```java
The element mismatched at index: 1
```

## 示例 15: `parallelSort(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.parallelSort() method

// Importing Arrays class from
// java.util package
import java.util.Arrays;

// Main class
public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using parallelSort
        Arrays.parallelSort(intArr);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]
```

## 示例 16: `sort(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.sort() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort-
        Arrays.sort(intArr);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]
```

## 示例 17: `sort(originalArray, fromIndex, endIndex)` 方法

```java
// Java program to demonstrate
// Arrays.sort() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        Arrays.sort(intArr, 1, 3);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]
```

## 示例 18: `sort(T[] a, int fromIndex, int toIndex, Comparator<? super T> c)` 方法

## Java 语言

### 示例 19: `Arrays.sort(T[] a, Comparator<? super T> c)` 方法

```java
// Java program to demonstrate working of Comparator
// interface
import java.util.*;
import java.lang.*;
import java.io.*;

// A class to represent a student.
class Student {
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name,
                   String address)
    {
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Used to print student details in main()
    public String toString()
    {
        return this.rollno + " "
            + this.name + " "
            + this.address;
    }
}

class Sortbyroll implements Comparator<Student> {
    // Used for sorting in ascending order of
    // roll number
    public int compare(Student a, Student b)
    {
        return a.rollno - b.rollno;
    }
}

// Driver class
class Main {
    public static void main(String[] args)
    {
        Student[] arr = { new Student(111, "bbbb", "london"),
                          new Student(131, "aaaa", "nyc"),
                          new Student(121, "cccc", "jaipur") };

        System.out.println("Unsorted");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);

        Arrays.sort(arr, 1, 2, new Sortbyroll());

        System.out.println("\nSorted by rollno");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);
    }
}
```

**Output**

```java
Unsorted
111 bbbb london
131 aaaa nyc
121 cccc jaipur

Sorted by rollno
111 bbbb london
131 aaaa nyc
121 cccc jaipur
```

### 示例 20: `Arrays.spliterator(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.spliterator() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        System.out.println("Integer Array: "
                           + Arrays.spliterator(intArr));
    }
}
```

**Output**

```java
Integer Array: java.util.Spliterators$IntArraySpliterator@4e50df2e
```

### 示例 21: `Arrays.spliterator(originalArray, fromIndex, endIndex)` 方法

```java
// Java program to demonstrate
// Arrays.spliterator() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        System.out.println("Integer Array: "
                           + Arrays.spliterator(intArr, 1, 3));
    }
}
```

**Output**

```java
Integer Array: java.util.Spliterators$IntArraySpliterator@4e50df2e
```

### 示例 22: `Arrays.stream(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.stream() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To get the Stream from the array
        System.out.println("Integer Array: "
                           + Arrays.stream(intArr));
    }
}
```

**Output**

```java
Integer Array: java.util.stream.IntPipeline$Head@7291c18f
```

### 示例 23: `Arrays.toString(originalArray)` 方法

```java
// Java program to demonstrate
// Arrays.toString() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To print the elements in one line
        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 20, 15, 22, 35]
```

本文由**里沙布·马赫塞**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论。