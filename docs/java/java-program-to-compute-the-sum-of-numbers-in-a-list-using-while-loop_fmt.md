# 使用 While-Loop 计算列表中数字总和的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-numbers-in-a-list-using-while-loop/](https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-numbers-in-a-list-using-while-loop/)

任务是在循环的同时使用[While-Loop](https://www.geeksforgeeks.org/java-while-loop-with-examples/)计算[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中数字的总和。`List`接口提供了一种存储有序集合的方式。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。

## 方法

*   创建列表。
*   创建两个`int`变量，一个用于存储数组的和，第二个用于帮助我们执行`while`循环。
*   在列表中添加一些元素。
*   执行`while`循环，直到计数变量小于列表的大小。
*   使用`get()`方法逐个获取列表元素，并用`sum`变量累加元素。
*   递增计数变量。

## 代码

```java
// Java Program to Compute the Sum of Numbers in a List
// Using While-Loop

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

// create a list
        List<Integer> list = new ArrayList<Integer>();
        int sum = 0;
        int count = 0;

// add some elements in list
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

// execute while loop until the count less then the
        // list size.
        while (list.size() > count) {

// add list values with sum variable one-by-one.
            sum += list.get(count);

// increment in count variable
            count++;
        }

// print sum variable
        System.out.println(" The sum of list is: " + sum);
    }
}
```

## 输出

```java
 The sum of list is: 15
```