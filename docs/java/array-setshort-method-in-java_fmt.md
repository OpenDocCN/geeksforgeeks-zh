# Java 中的数组 setShort()方法

> 原文: [https://www.geeksforgeeks.org/array-setshort-method-in-java/](https://www.geeksforgeeks.org/array-setshort-method-in-java/)

`java.lang.reflect.Array.setShort()` 是 Java 中的一个内置方法，用于将指定的短值设置为给定对象数组的指定索引。

## 语法

```java
Array.setShort(Object[] array, int index, short value)
```

## 参数

该方法取 3 个参数:

*   `array`: 这是一个将要更新的 `Object` 类型的数组。
*   `index`: 这是要更新的数组的索引。
*   `value`: 这是在给定的 `array` 的给定 `index` 处设置的短值。

## 异常

该方法抛出以下异常:

*   `NullPointerException` – 当数组为空时。
*   `IllegalArgumentException` – 当给定的对象数组不是数组时。
*   `ArrayIndexOutOfBoundsException` – 如果给定的索引不在数组大小的范围内。

下面是 `Array.setShort()` 方法的实现:

### 程序 1

```java
// Java code to demonstrate
// setShort() method of Array class

import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining Short array
        short b[] = {1, 2, 3, 4};
        System.out.print("Befor Set : ");
        // printing the array
        for (short x : b) {
            System.out.print(x + " ");
        }
        short value = 10;
        // set method of class Array
        Array.setShort(b, 1, value);

        System.out.print("\nAfter Set : ");
        // printing array
        for (short x : b) {
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```java
Befor Set : 1 2 3 4
After Set : 1 10 3 4
```

### 程序 2

演示 `java.lang.NullPointerException`

```java
// Java code to demonstrate
// setShort() method of Array class

import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining Short array to null
        short b[] = null;
        try {
            short s = 10;
            Array.setShort(b, 5, s);
        } catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException
```

### 程序 3

演示 `java.lang.ArrayIndexOutOfBoundsException`

```java
// Java code to demonstrate
// setShort() method of Array class

import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining Short array
        short b[] = {1, 2, 3, 4};
        try {
            short s = 10;
            Array.setShort(b, 5, s);
        } catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException
```

### 程序 4

演示 `java.lang.IllegalArgumentException`

```java
// Java code to demonstrate
// setShort() method of Array class

import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining Short variable
        short b = 1;
        try {
            short s = 10;
            Array.setShort(b, 5, s);
        } catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array
```