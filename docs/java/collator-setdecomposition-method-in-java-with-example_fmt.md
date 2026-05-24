# Java 中的 Collator.setDecomposition() 方法示例

> 原文：[https://www.geeksforgeeks.org/collator-setdecomposition-method-in-java-with-example/](https://www.geeksforgeeks.org/collator-setdecomposition-method-in-java-with-example/)

`java.text.Collator` 类的 `setDecomposition()` 方法用于设置该 `Collator` 的分解模式。

**语法：**
```java
public void setDecomposition(int decompositionMode)
```

**参数：** 该方法以 `int` 值作为参数，代表该整理器的等效分解模式。
**返回值：** 这个方法没有返回值。

以下是举例说明 `setDecomposition()` 方法：

## 示例 1

```java
// Java program to demonstrate
// setDecomposition() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // setting decomposition mode
            // into the Collator object
            // using setDecomposition() mehtod
            col.setDecomposition(
                Collator.CANONICAL_DECOMPOSITION);

            // getting decomposition mode
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode"
                    + " is :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is"
                    + " :- CANONICAL_DECOMPOSITION");
            else
                System.out.println(
                    "decompostiton mode is "
                    + ":- FULL_DECOMPOSITION. ");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
decompostiton mode is :- CANONICAL_DECOMPOSITION
```

## 示例 2

```java
// Java program to demonstrate
// setDecomposition() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance(Locale.UK);

            // setting decomposition mode
            // into the Collator object
            // using setDecomposition() mehtod
            col.setDecomposition(Collator.FULL_DECOMPOSITION);

            // getting decompostiton mode
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode"
                    + " is :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is"
                    + " :- CANONICAL_DECOMPOSITION");
            else
                System.out.println(
                    "decompostiton mode is "
                    + ":- FULL_DECOMPOSITION. ");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
decompostiton mode is :- FULL_DECOMPOSITION.
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#setDecomposition-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#setDecomposition-int-)