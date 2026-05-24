# Java Guava | `Bytes.indexOf(byte[] array, byte target)` 方法示例

> 原文: [https://www.geeksforgeeks.org/java-guava-bytes-indexofbyte-array-byte-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-indexofbyte-array-byte-target-method-with-examples/)

Guava [`Bytes`](https://www.geeksforgeeks.org/bytes-class-guava-java/) 类的 `Bytes.indexOf(byte[] array, byte target)` 方法接受两个参数 `array` 和 `target`。如果 `target` 存在于 `array` 中，该方法返回其第一次出现的位置。如果数组中不存在 `target`，则该方法返回 `-1`。

## 语法

```java
public static int indexOf(byte[] array, byte target)
```

## 参数

该方法接受两个参数：

*   `array`：是检查目标数组索引的整数数组。
*   `target`：是在指定数组中作为元素搜索的值。

## 返回值

该方法返回一个整数值，情况如下：

*   如果目标存在于数组中，则返回目标首次出现的位置。
*   否则，如果数组中没有目标，则返回 `-1`。

## 异常

该方法不抛出任何异常。

下面的例子说明了上述方法的实现：

### 例 1

```java
// Java code to show implementation of
// Guava's Bytes.indexOf(byte[] array,
// byte target) method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an byte array
        byte[] arr = { 1, 2, 3, 4, 3, 5 };

        byte target = 3;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Bytes.indexOf(byte[] array, byte target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Bytes.indexOf(arr, target);

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

输出:

```java
Array: [1, 2, 3, 4, 3, 5]
Target: 3
Target is present at index 2
```

### 例 2

```java
// Java code to show implementation of
// Guava's Bytes.indexOf(byte[] array,
// byte target) method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an byte array
        byte[] arr = { 3, 5, 7, 11, 13 };

        byte target = 23;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Bytes.indexOf(byte[] array, byte target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Bytes.indexOf(arr, target);

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

输出:

```java
Array: [3, 5, 7, 11, 13]
Target: 23
Target is not present in the array
```

参考: [https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#indexOf(byte[], %20byte)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#indexOf(byte[], %20byte))