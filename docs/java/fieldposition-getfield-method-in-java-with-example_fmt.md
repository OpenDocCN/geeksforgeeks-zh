# Java 中的 `FieldPosition.getField()` 方法示例

> 原文：[https://www.geeksforgeeks.org/fieldposition-getfield-method-in-java-with-example/](https://www.geeksforgeeks.org/fieldposition-getfield-method-in-java-with-example/)

`java.text.FieldPosition` 类的 `getField()` 方法用于检索该字段位置对象的字段标识符。

**语法：**
```java
public int getField()
```

**参数：** 该方法不接受任何参数。
**返回值：** 该方法返回该字段位置对象的字段标识。

以下是举例说明 `getField()` 方法：

## 示例 1

```java
// Java program to demonstrate
// getField() method

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

            // getting Field attribute
            // of FieldPosition object
            // using getField() method
            int i = pos.getField();

            // display result
            System.out.println(
                "field attribute :- "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
field attribute :- -1
```

## 示例 2

```java
// Java program to demonstrate
// getField() method

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

            // getting Field attribute
            // of FieldPosition object
            // using getField() method
            int i = pos.getField();

            // display result
            System.out.println(
                "field attribute :- "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
field attribute :- -1
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#getField--](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#getField--)