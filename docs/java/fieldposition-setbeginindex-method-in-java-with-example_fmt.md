# Java 中的 `FieldPosition.setBeginIndex()` 方法示例

> 原文：[`https://www.geeksforgeeks.org/fieldposition-setbeginindex-method-in-java-with-example/`](https://www.geeksforgeeks.org/fieldposition-setbeginindex-method-in-java-with-example/)

`java.text.FieldPosition` 类的 `setBeginIndex()` 方法用于设置 `FieldPosition` 对象开始字符的索引。

**语法：**
```java
public void setBeginIndex(int index)
```

**参数：** 该方法取 `int` 值作为 `FieldPosition` 对象起始字符的新索引。
**返回值：** 这个方法没有返回值。

以下是举例说明 `setBeginIndex()` 方法：

## 示例 1

```java
// Java program to demonstrate
// setBeginIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos
                = new FieldPosition(DateFormat.Field.AM_PM);

            // setting begin index of FieldPosition Object
            // using setBeginIndex() method
            pos.setBeginIndex(5);

            // getting begin index of FieldPosition Object
            int i = pos.getBeginIndex();

            // display result
            System.out.println("begin index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
begin index :- 5
```

## 示例 2

```java
// Java program to demonstrate
// setBeginIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos
                = new FieldPosition(
                    MessageFormat.Field.ARGUMENT);

            // setting begin index of FieldPosition Object
            // using setBeginIndex() method
            pos.setBeginIndex(10);

            // getting begin index of FieldPosition Object
            int i = pos.getBeginIndex();

            // display result
            System.out.println("begin index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
begin index :- 10
```

**参考：** [`https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#setBeginIndex-int-`](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#setBeginIndex-int-)