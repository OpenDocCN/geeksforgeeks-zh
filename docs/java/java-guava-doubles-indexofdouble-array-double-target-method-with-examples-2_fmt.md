# Java Guava | Doubles.indexOf(double[] array, double target) 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-doubles-indexofdouble-array-double-target-method-with-examples-2/](https://www.geeksforgeeks.org/java-guava-doubles-indexofdouble-array-double-target-method-with-examples-2/)

`Doubles.indexOf` 是 Guava [`Doubles`](https://www.geeksforgeeks.org/doubles-class-guava-java/) 类的一个方法，接受两个参数 `array` 和 `target`。如果目标存在于数组中，该方法返回其第一次出现的位置。如果数组中不存在目标，则该方法返回 `-1`。

## 语法：

`public static int indexOf(double[] array, double target)`

## 参数：
该方法接受两个参数：

*   `array`：是检查目标值索引的 double 数组。
*   `target`：是在指定数组中作为元素搜索的值。

## 返回值：
该方法返回一个整数值，情况如下：

*   如果目标存在于数组中，则返回目标首次出现的位置。
*   否则，如果数组中没有目标，则返回 `-1`。

## 异常：
该方法不抛出任何异常。

下面的例子说明了上述方法的实现：

## 例 1：

```java
// Java code to show implementation of
// Guava's Doubles.indexOf(double[] array,
// double target) method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an double array
        double[] arr = { 3.2, 5.3, 7.4, 11.4, 13.5 };

        double target = 7.4;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Doubles.indexOf(double[] array, double target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Doubles.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present "
                               + "in the array");
        }
    }
}
```

## 输出：

```java
Array: [3.2, 5.3, 7.4, 11.4, 13.5]
Target: 7.4
Target is present at index 2
```

## 例 2：

```java
// Java code to show implementation of
// Guava's Doubles.indexOf(double[] array,
// double target) method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an double array
        double[] arr = { 3, 5, 7, 11, 13 };

        double target = 23;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Doubles.indexOf(double[] array, double target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Doubles.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

## 输出：

```java
Array: [3.0, 5.0, 7.0, 11.0, 13.0]
Target: 23.0
Target is not present in the array
```

## 参考：
[https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#indexOf(double[], %20double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#indexOf(double[], %20double))