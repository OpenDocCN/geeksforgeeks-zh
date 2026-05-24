# Java 中的数组 getBoolean()方法

> 原文: [https://www.geeksforgeeks.org/array-getboolean-method-in-java/](https://www.geeksforgeeks.org/array-getboolean-method-in-java/)

`java.lang.reflect.Array.getBoolean()` 方法将指定数组中给定索引处的元素作为 `boolean` 类型返回。

## 语法

```java
Array.getBoolean(Object[] array, int index)
```

## 参数

*   `array`: 要返回其索引的对象数组。
*   `index`: 给定数组的特定索引。返回给定数组中 `index` 处的元素。

## 返回类型

该方法将数组的元素返回为 `boolean` 值。

## 注意

类型转换不是必需的，因为返回类型是 `boolean`。

## 异常

该方法抛出以下异常：

*   `NullPointerException` – 当数组为 `null` 时。
*   `IllegalArgumentException` – 当给定的对象不是数组时。
*   `ArrayIndexOutOfBoundsException` – 如果给定的索引不在数组的大小范围内。

下面的程序说明了 `Array` 类的 `getBoolean()` 方法：

### 程序 1

```java
// Java code to demonstrate getBoolean() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean array
        boolean a[] = {true,true,false};
        // Traversing the array
        for(int i = 0;i<3;i++){
            // Array.getBoolean() method
            boolean x = Array.getBoolean(a, i);
            // Printing the values
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```java
true true false
```

### 程序 2

```java
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean array
        boolean a[] = {true,true,false};
        try {
            // invalid index
            boolean x = Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException
```

### 程序 3

```java
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean array to null
        boolean a[] = null;
        try {
            // null Object array
            boolean x = Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException
```

### 程序 4

```java
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean variable
        boolean a = true;
        try {
            // illegalArgument
            boolean x = Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array
```