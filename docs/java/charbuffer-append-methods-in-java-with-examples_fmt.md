# Java 中的 CharBuffer append() 方法示例

> 原文：[https://www.geeksforgeeks.org/charbuffer-append-methods-in-java-with-examples/](https://www.geeksforgeeks.org/charbuffer-append-methods-in-java-with-examples/)

## 追加（字符 c）

`java.nio.CharBuffer` 类的 `append(char c)` 方法用于将指定的 `char` 追加到该缓冲区（可选操作）。
调用 `dst.append(c)` 形式的此方法的行为与调用 `dst.put(c)` 完全相同。

**语法：**
```java
public CharBuffer append(char c)
```

**参数：** 该方法采用 16 位字符追加。
**返回值：** 这个方法返回这个缓冲区，其中插入了字符值。
**异常：** 此方法抛出以下异常：

*   `BufferOverflowException` - 如果该缓冲区空间不足
*   `ReadOnlyBufferException` - 如果此缓冲区是只读的

以下是说明 `append(char c)` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// append() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer charbuffer
                = CharBuffer.allocate(capacity);

            // append the value in CharBuffer
            // using append() method
            charbuffer.append('a')
                .append('b')
                .append('c')
                .rewind();

            // print the CharBuffer
            System.out.println("Original CharBuffer:  "
                               + Arrays.toString(
                                     charbuffer.array()));
        }

        catch (BufferOverflowException e) {

            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**
```java
Original CharBuffer:  [a, b, c]
```