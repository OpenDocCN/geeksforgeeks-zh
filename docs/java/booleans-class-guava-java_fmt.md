# Booleans类|Guava|Java

> 原文：[https://www.geeksforgeeks.org/booleans-class-guava-java/](https://www.geeksforgeeks.org/booleans-class-guava-java/)

`Booleans`是一个用于基元类型布尔的实用程序类。它提供了属于布尔原语的静态实用方法，这些方法在`Boolean`或`Arrays`中都找不到。

## 申报

```java
@GwtCompatible(emulated=true)
public final class Booleans
extends Object 
```

## 下面给出的是Guava类提供的一些方法
![](img/b82f16460c4d67a34144e9ce94ee818b.png)

## 例外

*   **ensureCapacity**：如果最小长度或填充值为负，则显示“异常”。
*   **toArray**：`NullPointerException`如果集合或其任何元素为空。

## 下表显示了Guava Booleans类提供的一些其他方法
![](img/90f229697fdfe9ebf23f07dbc19c3c79.png)

下面给出了一些示例，显示了Guava Booleans类方法的实现：

### 示例 1

```java
// Java code to show implementation
// of Guava Booleans.asList() method

import com.google.common.primitives.Booleans;
import java.util.*;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        boolean arr[] = { true, false, true, false, true };

        // Using Booleans.asList() method which
        // converts array of primitives to array of objects
        List<Boolean> myList = Booleans.asList(arr);

        // Displaying the elements
        System.out.println(myList);
    }
}
```

**输出：**

```java
[true, false, true, false, true] 
```

### 示例 2

```java
// Java code to show implementation
// of Guava Booleans.toArray() method

import com.google.common.primitives.Booleans;
import java.util.*;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        List<Boolean> myList = Arrays.asList(true, false, true, false, true);

        // Using Booleans.toArray() method which
        // converts a List of Booleans to an
        // array of boolean
        boolean[] arr = Booleans.toArray(myList);

        // Displaying the elements
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出：**

```java
[true, false, true, false, true] 
```

### 示例 3

```java
// Java code to show implementation
// of Guava Booleans.concat() method

import com.google.common.primitives.Booleans;
import java.util.*;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        boolean[] arr1 = { true, false, true };
        boolean[] arr2 = { false, true };

        // Using Booleans.concat() method which
        // combines arrays from specified
        // arrays into a single array
        boolean[] arr = Booleans.concat(arr1, arr2);

        // Displaying the elements
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出：**

```java
[true, false, true, false, true] 
```

### 示例 4

```java
// Java code to show implementation
// of Guava Booleans.contains() method

import com.google.common.primitives.Booleans;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        boolean[] arr = { true, false, true, false, true };

        // Using Booleans.contains() method which
        // checks if element is present in array
        // or not
        System.out.println(Booleans.contains(arr, true));
        System.out.println(Booleans.contains(arr, false));
    }
}
```

**输出：**

```java
true
true 
```

### 示例 5

```java
// Java code to show implementation
// of Guava Booleans.compare() method

import com.google.common.primitives.Booleans;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        // To compare true vs true
        System.out.println(Booleans.compare(true, true));
    }
}
```

**输出：**

```java

```

### 示例 6

```java
// Java code to show implementation
// of Guava Booleans.indexOf() method

import com.google.common.primitives.Booleans;

class GFG {
    // Driver method
    public static void main(String[] args)
    {
        boolean[] arr = { true, false, true, false, true };

        // To print index of first occurence of false
        System.out.println(Booleans.indexOf(arr, false));
    }
}
```

**输出：**

```java

```