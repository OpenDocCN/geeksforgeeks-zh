# Java 中 BreakIterator.setText(String) 方法示例

> 原文：[https://www.geeksforgeeks.org/breakiterator-settextstring-method-in-java-with-examples/](https://www.geeksforgeeks.org/breakiterator-settextstring-method-in-java-with-examples/)

`java.text.BreakIterator` 类的 `setText()` 方法用于将新文本设置到 `BreakIterator` 中。

## 语法

```java
public void setText(String newText)
```

## 参数
该方法以字符串形式的 `text` 为参数。

## 返回值
此方法不返回任何内容。

以下是举例说明 `setText()` 方法：

### 例 1

```java
// Java program to demonstrate setText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        // using setText() method
        wb.setText("Code Geeks");

        // getting the text being scanned by
        // using getText() method
        StringCharacterIterator text
            = (StringCharacterIterator)wb.getText();

        // display the result
        System.out.print("Retrieved text is : "
                         + text.first());
        for (int i = text.getBeginIndex() - 1;
             i < text.getEndIndex() - 2;
             i++)
            System.out.print(text.next());
    }
}
```

**Output**

```java
Retrieved text is : Code Geeks
```

### 例 2

```java
// Java program to demonstrate setText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        // using setText() method
        wb.setText("GeeksForGeeks");

        // getting the text being scanned by
        // using getText() method
        StringCharacterIterator text
            = (StringCharacterIterator)wb.getText();

        // display the result
        System.out.print("Retrieved text is : "
                         + text.first());
        for (int i = text.getBeginIndex() - 1;
             i < text.getEndIndex() - 2;
             i++)
            System.out.print(text.next());
    }
}
```

**Output**

```java
Retrieved text is : GeeksForGeeks
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#first--](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#first--)