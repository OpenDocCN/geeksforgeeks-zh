# Java 中的数组 `setDouble()` 方法

> 原文：[https://www.geeksforgeeks.org/array-setdouble-method-in-java/](https://www.geeksforgeeks.org/array-setdouble-method-in-java/)

`java.lang.reflect.Array.setDouble()` 是 Java 中的一个内置方法，用于将指定的 double 值设置为给定对象数组的指定索引。

## 语法

```java
Array.setDouble(Object[] array, int index, double value)
```

## 参数

该方法取三个参数：

*   **`array`**：这是一个将要更新的 `Object` 类型的数组。
*   **`index`**：这是要更新的数组的索引。
*   **`value`**：这是在给定的 `array` 的给定 `index` 处设置的双倍值。

## 异常

该方法抛出以下异常：

*   **`NullPointerException`** – 当数组为空时。
*   **`IllegalArgumentException`** – 当给定的对象数组不是数组时。
*   **`ArrayIndexOutOfBoundsException`** – 如果给定的索引不在数组大小的范围内。

下面是 `Array.setDouble()` 方法的实现：

### 程序 1

```java
// Java code to demonstrate setDouble()
// method of Array class

import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // Declaring and defining double array
        double f[] = { 1.0, 2.0, 3.0 };

        // printing the array
        System.out.print("Before Set : ");
        for (double x : f) {
            System.out.print(x + " ");
        }

        double value = 400.0;

        // setDouble method of class Array
        Array.setDouble(f, 1, value);

        // printing array
        System.out.print("\nAfter Set : ");
        for (double x : f) {
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```java
Before Set : 1.0 2.0 3.0 
After Set : 1.0 400.0 3.0
```

### 程序 2

演示 `java.lang.NullPointerException`

```java
// Java code to demonstrate setDouble()
// method of Array class

import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // Declaring and defining double array to null
        double b[] = null;

        try {
            double c = 1.0;

            // setDouble method of class Array
            // passing null array in parameters
            Array.setDouble(b, 5, c);
        }
        catch (Exception e) {
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
// Java code to demonstrate setDouble()
// method of Array class

import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // Declaring and defining double array
        double b[] = { 1.0, 2.0, 3.0 };

        try {
            double c = 1.0;

            // setDouble method of class Array
            // passing index 5 when size is 3
            Array.setDouble(b, 5, c);
        }
        catch (Exception e) {
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
// Java code to demonstrate setDouble()
// method of Array class

import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // Declaring and defining double variable
        double b = 2.0;
        try {
            double c = 1.0;
            // setDouble method of class Array
            // passing a variable as parameter
            // when an array is required instead
            Array.setDouble(b, 5, c);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array
```