# Java 中的 MessageFormat hashCode()方法示例

> 原文：[https://www.geeksforgeeks.org/messageformat-hashcode-method-in-java-with-example/](https://www.geeksforgeeks.org/messageformat-hashcode-method-in-java-with-example/)

`java.text.MessageFormat` 类的 `hashCode()` 方法用于获取该消息格式对象的哈希码。

**语法：**

```java
public int hashCode()
```

**参数：** 该方法不接受任何参数。
**返回值：** 这个方法返回这个消息格式对象的哈希代码。

以下是说明 `hashCode()` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // getting hash code
        // for this MessageFormat Object
        // using hashCode() method
        int hash = mf.hashCode();

        // display the result
        System.out.println("Hashcode is : " + hash);
    }
}
```

**输出：**

```java
Hashcode is : 1408
```

### 示例 2

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {4, time}");

        // getting hash code
        // for this MessageFormat Object
        // using hashCode() method
        int hash = mf.hashCode();

        // display the result
        System.out.println("Hashcode is : " + hash);
    }
}
```

**输出：**

```java
Hashcode is : 44
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#hashCode--](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#hashCode--)