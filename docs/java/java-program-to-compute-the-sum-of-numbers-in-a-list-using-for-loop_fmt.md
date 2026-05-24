# 使用 For 循环计算列表中数字总和的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-numbers-in-a-list-using-for-loop/](https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-numbers-in-a-list-using-for-loop/)

给定一个数字列表，编写一个 Java 程序，找出使用 for 循环的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中所有元素的总和。为了执行给定的任务，完整的列表遍历是必要的，这使得整个程序的时间复杂度为 `O(n)`，其中 `n` 是列表的长度。

**例：**

```java
Input : List = [1, 2, 3]
Output: Sum = 6

Input : List = [5, 1, 2, 3]
Output: Sum = 11
```

## 方法 1

1.  创建 `sum` 和 `i` 变量，数据类型为整数。
2.  将 `sum` 和 `i` 初始化为 0。
3.  使用 for 循环开始迭代 `list`。
4.  在迭代过程中，将每个元素与 `sum` 和 `i` 变量相加。
5.  循环执行完毕后，打印总和。

下面是上述方法的实现：

### Java 实现

```java
// Java Program to Compute the Sum of
// Numbers in a List Using For-Loop
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(10);
        list.add(9);
        int sum = 0;
        for (int i = 0; i < list.size(); i++)
            sum += list.get(i);

        System.out.println("sum-> " + sum);
    }
}
```

**输出**

```java
sum-> 37
```

**时间复杂度：** `O(n)`

## 方法 2

1.  创建 `sum` 和 `i` 变量，数据类型为整数。
2.  将 `sum` 和 `i` 初始化为 0。
3.  使用增强 for 循环开始迭代 `list`。
4.  在迭代过程中，将每个元素与 `sum` 和 `i` 变量相加。
5.  循环执行完毕后，打印总和。

下面是上述方法的实现：

### Java 实现

```java
// Java Program to Compute the Sum of
// Numbers in a List Using Enhanced For-Loop
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(10);
        list.add(9);
        int sum = 0;
        for (Integer i : list)
            sum += i;

        System.out.println("sum-> " + sum);
    }
}
```

**输出**

**时间复杂度：** `O(n)`