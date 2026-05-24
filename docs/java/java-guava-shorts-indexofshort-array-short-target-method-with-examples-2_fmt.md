# Java Guava Shorts.indexOf方法详解与示例

> 原文：[https://www.geeksforgeeks.org/java-guava-shorts-indexofshort-array-short-target-method-with-examples-2/](https://www.geeksforgeeks.org/java-guava-shorts-indexofshort-array-short-target-method-with-examples-2/)

`Shorts.indexOf(short[] array, short target)`方法是Guava的[`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/)类接受两个参数`array`和`target`。如果目标存在于数组中，该方法返回其第一次出现的位置。如果数组中不存在目标，则该方法返回`-1`。

## 语法

```java
public static int indexOf(short[] array, short target)
```

## 参数

该方法接受两个参数：

*   `array`：是检查目标数组索引的整数数组。
*   `target`：是在指定数组中作为元素搜索的值。

## 返回值

该方法返回一个整数值如下：

*   如果目标存在于数组中，则返回目标首次出现的位置。
*   否则，如果数组中没有目标，则返回`-1`。

## 异常

该方法不抛出任何异常。

下面的例子说明了上述方法的实现：

### 例 1

```java
// Java code to show implementation of
// Guava's Shorts.indexOf(short[] array,
// short target) method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an short array
        short[] arr = { 1, 2, 3, 4, 3, 5 };

        short target = 3;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Shorts.indexOf(short[] array, short target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Shorts.indexOf(arr, target);

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

输出：

```java
Array: [1, 2, 3, 4, 3, 5]
Target: 3
Target is present at index 2
```

### 例 2

```java
// Java code to show implementation of
// Guava's Shorts.indexOf(short[] array,
// short target) method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an short array
        short[] arr = { 3, 5, 7, 11, 13 };

        short target = 23;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Shorts.indexOf(short[] array, short target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Shorts.indexOf(arr, target);

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

输出：

```java
Array: [3, 5, 7, 11, 13]
Target: 23
Target is not present in the array
```

参考：[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#indexOf-short:A-short-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#indexOf-short:A-short-)