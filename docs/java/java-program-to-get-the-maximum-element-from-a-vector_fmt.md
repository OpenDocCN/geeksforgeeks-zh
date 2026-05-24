# 从向量中获取最大元素的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-get-the-maximum-element-from-a-vector/](https://www.geeksforgeeks.org/java-program-to-get-the-maximum-element-from-a-vector/)

## 先决条件

[Java 中的向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)

## 我们为什么要使用向量？

到目前为止，我们已经学会了两种方法来声明数组：一个固定大小的数组，或者根据用户的需求在内存中分配一个可变大小的数组。

```java
int Array_name[Fixed_size] ;
int array_name[variable_size] ;
```

为了正确利用内存并优化，我们引入了向量，避免了上述两种方法可能造成的内存浪费。

## 使用向量的优势

*   动态大小
*   丰富的库函数
*   易于理解的大小
*   无需传递大小参数。
*   可以从函数中返回。
*   默认使用默认值。

## 丰富的库函数包括

1.  查找元素
2.  删除元素
3.  插入元素

这里，我们使用丰富的库函数来获取最大元素。

**注意:** 数组总是作为指针传递，因此您必须传递数组的大小，但在向量的情况下，这不是必需的。

## 语法

在数组的情况下

```java
type function_Name(type arrayName[], type sizeOfArray) ;
```

在向量的情况下

```java
type function_Name(vector<type> vectorName) ;
```

考虑一个给定向量的例子，任务是找到最大元素。

## 示例

> **输入:** `v1={1, 2, 3, 4, 5}`
> 
> **输出:** `5`
> 
> **输入:** `v2={7, 50, 0, 67, 98}`
> 
> **输出:** `98`

### 方法 1: 使用预定义函数

*   首先，我们将初始化一个向量，比如 `v`，然后我们将在这个向量中存储值。
*   之后，我们将调用在 `java.util.Collections` 类中定义的预定义方法 `max()`。
*   打印最大元素。

以下是实现上述方法的代码。

```java
// Java Program to find maximum element
// in a vector using predefined method

import java.io.*;

// Importing Vector Class
import java.util.Collections;

// Importing Vector Class
import java.util.Vector;

class GFG {

    // Main Method
    public static void main(String[] args)
    {
        // initializing a Vector
        Vector<Integer> v = new Vector<Integer>();

        // adding values to the Vector
        v.add(7);
        v.add(50);
        v.add(0);
        v.add(67);
        v.add(98);

        // finding the largest element
        int n = Collections.max(v);

        // printing the largest element
        System.out.println(
            "The maximum value present in Vector is : "
            + n);
    }
}
```

**输出:**

```java
The maximum value present in Vector is : 98
```

**最坏情况时间复杂度:** `O(n)`，其中 `n` 是向量中存在的元素数量。

### 方法 2: 比较向量中存在的每个元素

*   首先，我们将初始化一个向量，比如 `v`，然后我们将在这个向量中存储值。
*   接下来，我们取一个变量，让我们说 `maxNumber`，赋一个可能的最小值。
*   遍历到向量的末尾，将向量的每个元素与 `maxNumber` 进行比较。
*   如果向量中存在的元素大于 `maxNumber`，则将 `maxNumber` 更新为该值。
*   打印 `maxNumber`。

下面是上述方法的实现。

```java
// Java Program to find maximum element
// in a vector by comparing each element

import java.io.*;

// Importing Vector Class
import java.util.Vector;

class GFG {

    // Main Method
    public static void main(String[] args)
    {
        // initializing a Vector
        Vector<Integer> v = new Vector<Integer>();

        // adding values to the Vector
        v.add(1);
        v.add(2);
        v.add(3);
        v.add(4);
        v.add(5);

        // Store the first element as maxNumber
        int maxNumber = v.get(0);

        // Iterate through the vector
        for (int i = 1; i < v.size(); i++) {

            // Compare each element with maxNumber
            if (v.get(i) > maxNumber) {
                // Update maxNumber if a larger element is found
                maxNumber = v.get(i);
            }
        }

        // Print the largest element
        System.out.println(
            "The largest element present in Vector is : "
            + maxNumber);
    }
}
```

**输出:**

```java
The largest element present in Vector is : 5
```

**时间复杂度:** `O(n)`，其中 `n` 为向量中存在的元素个数。