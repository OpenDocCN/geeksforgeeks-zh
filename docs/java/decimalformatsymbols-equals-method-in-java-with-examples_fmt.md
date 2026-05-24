# Java 中的 DecimalFormatSymbols.equals() 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-equals-method-in-java-with-examples/)

`equals()`方法在 Java 的 `DecimalFormatSymbols` 类中用于检查此 `DecimalFormatSymbols` 实例与指定的对象是否相等。此方法获取一个 `DecimalFormatSymbols` 实例，并将其与当前实例进行比较，然后返回一个表示内容是否相同的布尔值。

## 语法
```java
public boolean equals(Object obj)
```

## 参数
该方法接受一个参数 `Object obj`，该参数是要检查是否与当前 `DecimalFormatSymbols` 相等的对象。

## 返回值
这个方法返回一个 `boolean` 值，指示这个 `DecimalFormatSymbols` 是否等于指定的对象。

## 异常
这个方法不抛出任何异常。

## 程序示例
```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs1
            = new DecimalFormatSymbols();

        System.out.println("DecimalFormatSymbols 1: "
                           + dfs1);

        DecimalFormatSymbols dfs2
            = new DecimalFormatSymbols(
                new Locale("JAPANESE"));

        System.out.println("DecimalFormatSymbols 2: "
                           + dfs2);

        DecimalFormatSymbols dfs3
            = (DecimalFormatSymbols)dfs1.clone();

        System.out.println("DecimalFormatSymbols 3: "
                           + dfs3);

        System.out.println("Comparing DFS 1 and DFS 2: "
                           + dfs1.equals(dfs2));

        System.out.println("Comparing DFS 2 and DFS 3: "
                           + dfs2.equals(dfs3));

        System.out.println("Comparing DFS 1 and DFS 3: "
                           + dfs1.equals(dfs3));
    }
}
```

## 输出
```java
DecimalFormatSymbols 1: java.text.DecimalFormatSymbols@1073a
DecimalFormatSymbols 2: java.text.DecimalFormatSymbols@1073a
DecimalFormatSymbols 3: java.text.DecimalFormatSymbols@1073a
Comparing DFS 1 and DFS 2: false
Comparing DFS 2 and DFS 3: false
Comparing DFS 1 and DFS 3: true
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#equals-java.lang.Object-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#equals-java.lang.Object-)