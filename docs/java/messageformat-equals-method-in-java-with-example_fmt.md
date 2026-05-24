# Java 中的 MessageFormat equals()方法示例

> 原文：[https://www.geeksforgeeks.org/messageformat-equals-method-in-java-with-example/](https://www.geeksforgeeks.org/messageformat-equals-method-in-java-with-example/)

`java.text.MessageFormat` 类的 `equals()` 方法用于检查两个 `MessageFormat` 对象是否相同。

## 语法

```java
public boolean equals(Object obj)
```

## 参数
该方法取 `MessageFormat` 对象，与当前 `MessageFormat` 对象进行比较。

## 返回值
如果两个 `MessageFormat` 对象彼此相等，则返回 `true`，否则返回 `false`。

以下是举例说明 `equals()` 方法：

## 示例 1

```java
// Java program to demonstrate
// equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating and initializing MessageFormat
            MessageFormat mf1
                = new MessageFormat("{0, date, #}, {1, time, #}, {0, number}");

            // creating and initializing MessageFormat
            MessageFormat mf2
                = new MessageFormat("{0, date, #}, {1, time, #}, {0, number}");

            // compare both object
            // using equals() method
            boolean i = mf1.equals(mf2);

            // display result
            if (i)
                System.out.println(
                    "mf1 is equals to mf2");
            else
                System.out.println(
                    "mf1 is not equal to mf2");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

## 输出

```java
mf1 is equals to mf2
```