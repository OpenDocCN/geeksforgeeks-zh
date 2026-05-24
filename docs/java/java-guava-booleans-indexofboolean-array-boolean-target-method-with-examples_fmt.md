# Booleans.indexOf(boolean[] array, boolean[] target) 方法

> 原文：[https://www.geeksforgeeks.org/java-guava-booleans-indexofboolean-array-boolean-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-indexofboolean-array-boolean-target-method-with-examples/)

`Booleans.indexOf(boolean[] array, boolean[] target)` 是 Guava [`Booleans`](https://www.geeksforgeeks.org/booleans-class-guava-java/) 类中的一个方法。它接受两个参数：`array` 和 `target`。如果 `target` 存在于 `array` 中，该方法返回其第一次出现的起始位置。如果 `array` 中不存在 `target`，则该方法返回 `-1`。

## 语法

```java
public static int indexOf(boolean[] array,
                          boolean[] target)
```

## 参数

该方法接受两个参数：
*   `array`：要搜索的数组。
*   `target`：作为子序列在 `array` 中被搜索的数组。

## 返回值

该方法返回：
*   如果 `target` 存在于 `array` 中，则返回其第一次出现的起始位置。
*   如果 `target` 不在 `array` 中，则返回 `-1`。

## 异常

该方法不抛出任何异常。

## 示例

下面的例子说明了上述方法的实现：

### 示例 1

```java
// Java code to show implementation of
// Guava's Booleans.indexOf(boolean[] array,
// boolean[] target) method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a boolean array
        boolean[] arr = { false, true, false,
                          false, true };

        boolean[] target = { false, false };

        // Using indexOf(boolean[] array, boolean[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Booleans.indexOf(arr, target);

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

### 示例 2

```java
// Java code to show implementation of
// Guava's Booleans.indexOf(boolean[] array,
// boolean[] target) method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a boolean array
        boolean[] arr = { false, true, false,
                          false, true };

        boolean[] target = { false, false, false };

        // Using indexOf(boolean[] array, boolean[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Booleans.indexOf(arr, target);

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

## 参考

[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#indexOf-boolean:A-boolean:A-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#indexOf-boolean:A-boolean:A-)