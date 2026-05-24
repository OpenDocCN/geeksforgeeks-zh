# JavaTuples `containsAll()`方法

> 原文: [https://www.geeksforgeeks.org/java-tuples-containsall-method/](https://www.geeksforgeeks.org/java-tuples-containsall-method/)

`org.javatuples` 中的 `containsAll()` 方法用于检查 `TupleClass` 中是否存在作为参数给出的值集合。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个布尔值，该值基于 `TupleClass` 中值集合的存在与否。

## 方法声明

```java
public final boolean containsAll(Object... value)
```

## 语法

```java
boolean result = TupleClassObject.containsAll(X value1, X value2, ...)
                    OR
boolean result = TupleClassObject.containsAll(X[] values)
```

## 参数

该方法以*值或数值*为参数，其中:

*   `X` – 表示参数中值的数据类型。
*   `TupleClassObject` – 表示像 `Unit`、`Pair`、`Decade` 等使用的 JavaTuple 类对象。

## 返回值

如果元组中存在参数值，则该方法返回 `true`。否则返回 `false`。

下面的程序说明了使用 `containsAll()` 方法的各种方法:

## 示例程序

### 程序 1: 使用 `containsAll()` 搭配 `Unit` 类

```java
// Below is a Java program to use containsAll() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using containsAll() method
        boolean res;

        // for True result
        String[] check = { "GeeksforGeeks" };
        res = unit.containsAll(check);

        System.out.println("Is " + Arrays.toString(check) + " present : " + res);

        // for False result
        String[] check1 = { "Geeks", "for", "Geeks" };
        res = unit.containsAll(check1);

        System.out.println("Is " + Arrays.toString(check1) + " present : " + res);
    }
}
```

**输出:**

```java
Is [GeeksforGeeks] present : true
Is [Geeks, for, Geeks] present : false
```

### 程序 2: 使用 `containsAll()` 搭配 `Decade` 类

```java
// Below is a Java program to use containsAll() method

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Creating a Decade with 10 value
        Decade<String, String, String, String, String,
               String, String, String, String, String>
            decade = Decade.with("Geeks",
                                 "for",
                                 "Geeks",
                                 "A",
                                 "Computer",
                                 "Science",
                                 "Portal",
                                 "for",
                                 "Geeks",
                                 "RishabhPrabhu");

        // Using containsAll() method
        boolean res;

        // for true result
        String[] check = { "Geeks", "for", "Geeks" };
        res = decade.containsAll(check);

        System.out.println("Is " + Arrays.toString(check) + " present : " + res);

        // for False result
        String[] check1 = { "Geeks", "not", "for", "Geeks" };
        res = decade.containsAll(check1);

        System.out.println("Is " + Arrays.toString(check1) + " present : " + res);
    }
}
```

**输出:**

```java
Is [Geeks, for, Geeks] present : true
Is [Geeks, not, for, Geeks] present : false
```

**注:** 同样，它也可以搭配任何其他 JavaTuple 类使用。