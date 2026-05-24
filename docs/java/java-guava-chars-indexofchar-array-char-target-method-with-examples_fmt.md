# Java 番石榴 | `Chars.indexOf(char[] array, char[] target)` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-chars-indexofchar-array-char-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-indexofchar-array-char-target-method-with-examples/)

`Chars.indexOf(char[] array, char[] target)` 是 Guava 的 [`Chars`](https://www.geeksforgeeks.org/chars-class-guava-java/) 类中的一个方法，它接受两个参数 `array` 和 `target`。如果目标存在于数组中，则该方法返回其第一次出现的开始位置。如果数组中不存在目标，则该方法返回 `-1`。

## 语法

```java
public static int indexOf(char[] array, char[] target)
```

## 参数

该方法接受两个参数：

*   `array`：是检查目标数组索引的整数数组。
*   `target`：作为指定数组的子序列进行搜索的数组。

## 返回值

该方法返回如下整数值：

*   如果数组中存在目标数组，则返回目标首次出现的起始位置。
*   否则，如果数组中没有目标，则返回 `-1`。

## 异常

该方法不抛出任何异常。

下面的例子说明了上述方法的实现：

### 例 1

```java
// Java code to show implementation of
// Guava's Chars.indexOf(char[] array,
// char[] target) method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an char array
        char[] arr = { 'G', 'F', 'G', 'E', 'E' };

        char[] target = { 'E', 'E' };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Chars.indexOf(char[] array, char[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Chars.indexOf(arr, target);

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
Array: [G, F, G, E, E]
Target Array: [E, E]
Target is present at index 3
```

### 例 2

```java
// Java code to show implementation of
// Guava's Chars.indexOf(char[] array,
// char[] target) method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an char array
        char[] arr = { 'H', 'E', 'L', 'L', 'O' };

        char[] target = { 'G', 'E', 'E' };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Chars.indexOf(char[] array, char[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Chars.indexOf(arr, target);

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
Array: [H, E, L, L, O]
Target Array: [G, E, E]
Target is not present in the array
```

参考：[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Chars.html#indexOf-char:A-char:A-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Chars.html#indexOf-char:A-char:A-)