# 用示例选择 Java 中的 Format()方法

> 原文:[https://www . geesforgeks . org/choice format-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-format-method-in-java-with-examples/)

`Java.text.ChoiceFormat`类的`format()`方法用于获取该方法中作为参数传递的特定限值的格式值和作为参数传递的文本的追加字符串生成器。

## 语法:

```java
public StringBuffer format(double number,
                         StringBuffer toAppendTo,
                         FieldPosition status)
```

## 参数:

该方法取以下参数如下

*   `number`: 这是必须找到并附加格式的`ChoiceFormat`对象的特定限制
*   `toAppendTo`: 是要添加格式的新文本
*   `status`: 确定是否没有需要返回的特殊状态

## 返回值:

该方法以`StringBuffer`对象的形式返回文本和格式的附加值。

## 异常:

如果`toAppendTo`值为空，此方法抛出`NullPointerException`。

以下是举例说明`format()`方法:

### 例 1:

```java
// Java program to demonstrate
// format() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

// creating and initializing ChoiceFormat
            ChoiceFormat cf1
                = new ChoiceFormat(
                    "4#wed| 5#thu | 6#fri | 7#sat");

// creating and initializing StringBuffer
            StringBuffer str = new StringBuffer("Sun");

// getting the required format with appended text
            // ChoiceFormat Object
            // using format() method
            StringBuffer value = cf1.format(6, str, null);

// display the result
            System.out.print("Formated text with appended value: "
                             + value.toString());
        }
        catch (NullPointerException e) {
            System.out.println("str is null");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
Formated text with appended value: Sunfri 
```