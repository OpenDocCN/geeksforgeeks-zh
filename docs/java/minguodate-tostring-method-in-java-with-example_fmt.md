# Java 中的 MinguoDate toString()方法，示例

> 原文: [https://www.geeksforgeeks.org/minguodate-tostring-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-tostring-method-in-java-with-example/)

`java.time.chrono.MinguoDate`类的`toString()`方法用于将民国日期表示为字符串格式。

**语法:**
```java
public String toString()
```

**参数:** 该方法不接受任何参数作为参数。
**返回值:** 该方法将`MinguoDate`返回为字符串格式。

以下是举例说明`toString()`方法:

### 示例 1

```java
// Java program to demonstrate
// toString() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // Getting string representation
            // of Minguo date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Minguodate : "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**
```java
Minguodate : Minguo ROC 109-04-27
```

### 示例 2

```java
// Java program to demonstrate
// toString() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.of(1345, 05, 23);

            // Getting string representation
            // of Minguo date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Minguodate : "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**
```java
Minguodate : Minguo ROC 1345-05-23
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#toString--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#toString--)