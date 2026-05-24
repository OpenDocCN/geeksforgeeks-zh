# 打印数字总和的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-print-summation-of-numbers/](https://www.geeksforgeeks.org/java-program-to-print-summation-of-numbers/)

给定一个整数数组，打印数组中所有元素的总和。

## 示例：

> 输入：`arr[] = {1, 2, 3, 4, 5}`
> 
> 输出：15
> 
> 输入：`arr[] = {2, 9, -10, -1, 5, -12}`
> 
> 输出：-7

### 方法 1：数组中的迭代

1.  创建一个名为 `sum` 的变量，并将其初始化为 0。
2.  通过循环遍历数组，并将每个元素的值相加。
3.  打印总和作为答案。

下面是上述方法的实现。

### Java 实现

```java
// Java Program to print the sum 
// of all the elements in an array
class GFG {

    static int sumOfArray(int arr[])
    {
        // initialise sum to 0
        int sum = 0;

        // iterate through the array using loop
        for (int i = 0; i < arr.length; i++) {
            sum = sum + arr[i];
        }

        // return sum as the answer
        return sum;
    }

    // Driver code
    public static void main(String[] args)
    {
        // print the sum
        int arr[] = { 1, 2, 3, 4, -2, 5 };
        System.out.println(
            "The sum of elements of given array is: "
            + sumOfArray(arr));
    }
}
```

**Output**

```java
The sum of elements of given array is: 13
```

**时间复杂度：**`O(N)`，其中 `N` 为数组的大小。

### 方法 2：使用 `IntStream.of().sum()`

内置方法 `IntStream.of(arrayName).sum()` 用于对整数数组中的所有元素求和。

**语法：**

```java
IntStream.of(arrayName).sum();
```

下面是上述方法的实现。

### Java 实现

```java
// Java Program to print the sum 
// of all the elements in an array

// import IntStream
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // print the sum
        int arr[] = { 1, 2, 3, 4, -2, 5 };
        System.out.println(
            "The sum of elements of given array is: "
            + IntStream.of(arr).sum());
    }
}
```

**Output**

```java
The sum of elements of given array is: 13
```