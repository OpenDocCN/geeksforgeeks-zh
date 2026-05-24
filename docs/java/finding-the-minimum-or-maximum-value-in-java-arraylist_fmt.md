# 在 Java 数组列表中寻找最小值或最大值

> 原文: [https://www.geeksforgeeks.org/finding-the-minimum-or-maximum-value-in-java-arraylist/](https://www.geeksforgeeks.org/finding-the-minimum-or-maximum-value-in-java-arraylist/)

最小值为最小值，最大值为最大值。这里的主要任务是从[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中找到最小值和最大值。考虑一个数组列表的例子，我们需要找到最大和最小的元素。

`例:`

```java
Input List: {10, 20, 8, 32, 21, 31};

Output:

Maximum is: 32

Minimum is: 8
```

## 方法 1: 通过迭代数组列表值

1.  首先，我们需要初始化数组列表的值。
2.  然后使用 `size()` 函数来查找数组列表的长度。
3.  之后，数组列表的第一个元素将被存储在变量 `min` 和 `max` 中。
4.  然后使用 `for` 循环遍历数组列表的元素，逐一找出其中的最小值和最大值。

```java
// Java program to find the minimum and
// maximum value of the ArrayList

import java.util.*;
public class Max {
    public static void main(String args[])
    {

// initializing the ArrayList elements
        ArrayList<Integer> arr = new ArrayList<>();
        arr.add(10);
        arr.add(20);
        arr.add(8);
        arr.add(32);
        arr.add(21);
        arr.add(31);

int min = arr.get(0);
        int max = arr.get(0);

// store the length of the ArrayList in variable n
        int n = arr.size();

// loop to find minimum from ArrayList
        for (int i = 1; i < n; i++) {
            if (arr.get(i) < min) {
                min = arr.get(i);
            }
        }

// loop to find maximum from ArrayList
        for (int i = 1; i < n; i++) {
            if (arr.get(i) > max) {
                max = arr.get(i);
            }
        }

// The result will be printed
        System.out.println("Maximum is : " + max);
        System.out.println("Minimum is : " + min);
    }
}
```

`输出`

```java
Maximum is : 32
Minimum is : 8
```