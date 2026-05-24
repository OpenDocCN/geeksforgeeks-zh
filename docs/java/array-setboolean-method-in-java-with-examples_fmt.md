# Java 中的 `Array.setBoolean()` 方法示例

> 原文：[https://www.geeksforgeeks.org/array-setboolean-method-in-java-with-examples/](https://www.geeksforgeeks.org/array-setboolean-method-in-java-with-examples/)

`java.lang.reflect.Array.setBoolean()` 方法是一种内置方法，用于将指定的布尔值设置为给定对象数组的指定索引。

## 语法

```java
Array.setBoolean(Object[] array, int index, boolean value)
```

## 参数

该方法取三个参数：

*   `array`：待更新对象类型的数组。
*   `index`：要更新的数组的索引。
*   `value`：在给定的 `array` 的给定 `index` 处设置的布尔值。

## 返回类型

这是一个 `void` 类型的方法，不返回任何值。更新反映了作为参数传递的对象数组。

## 异常

该方法抛出以下异常：

*   `NullPointerException` – 当数组为空时。
*   `IllegalArgumentException` – 当给定的对象数组不是数组时。
*   `ArrayIndexOutOfBoundsException` – 如果给定的索引不在数组大小的范围内。

下面是 `Array.setBoolean()` 方法的实现：

### 程序 1

```java
// Java code to demonstrate setBoolean()
// method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining boolean array
        boolean b[] = { true, false, true };

        // array before using setBoolean()
        System.out.print("Before Set : ");

        // printing the array
        for (boolean x : b) {
            System.out.print(x + " ");
        }

        // boolean value to be set
        boolean value = true;

        // setBoolean method of class Array
        Array.setBoolean(b, 1, value);

        // array after using setBoolean()
        System.out.print("\nAfter Set : ");

        // printing array
        for (boolean x : b) {
            System.out.print(x + " ");
        }
    }
}
```

**输出：**

```java
Before Set : true false true 
After Set : true true true
```

### 程序 2：演示 `java.lang.NullPointerException`

```java
// Java code to demonstrate setBoolean()
// method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining boolean array to null
        boolean b[] = null;

        try {
            // boolean value to be set
            boolean c = false;

            // passing a null array as parameter
            Array.setBoolean(b, 5, c);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出：**

```java
Exception : java.lang.NullPointerException
```

### 程序 3：演示 `java.lang.ArrayIndexOutOfBoundsException`

```java
// Java code to demonstrate setBoolean()
// method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining boolean array
        boolean b[] = { true, false, true };

        try {
            // value to be set
            boolean c = false;

            // passing index as 5 when size is 3
            Array.setBoolean(b, 5, c);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出：**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException
```

### 程序 4：演示 `java.lang.IllegalArgumentException`

```java
// Java code to demonstrate setBoolean()
// method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining boolean variable
        boolean b = true;

        try {
            // value to be set
            boolean c = false;

            // passing variable in the place of an array
            Array.setBoolean(b, 5, c);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出：**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array
```