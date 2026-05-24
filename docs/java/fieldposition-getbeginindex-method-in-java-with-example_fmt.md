# Java 中的 FieldPosition getBeginIndex() 方法示例

> 原文：`https://www.geeksforgeks.org/fieldposition-getbeginindex-method-in-java-with-example/`

`java.text.FieldPosition` 类的 `getBeginIndex()` 方法用于获取 `FieldPosition` 对象开始字符的索引。

## 语法

```java
public int getBeginIndex()
```

## 参数

该方法不接受任何参数作为参数。

## 返回值

该方法返回 `FieldPosition` 对象开始字符的索引。

以下是说明 `getBeginIndex()` 方法的示例：

## 示例 1

```java
// Java program to demonstrate
// getBeginIndex() method

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
                    DateFormat.Field.AM_PM);

            // getting begin index of FieldPosition Object
            // using getBeginIndex() method
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
begin index :- 0
```

## 示例 2

```java
// Java program to demonstrate
// getBeginIndex() method

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
                    DateFormat.Field.AM_PM);

            // setting begin index
            pos.setBeginIndex(5);

            // getting begin index of FieldPosition Object
            // using getBeginIndex() method
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

**参考：** `https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#setBeginIndex-int-`