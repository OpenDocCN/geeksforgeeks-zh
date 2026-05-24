# 如何在 Java 中克隆列表？

> 原文：[https://www.geeksforgeeks.org/how-to-clone-a-list-in-java/](https://www.geeksforgeeks.org/how-to-clone-a-list-in-java/)

给定一个 Java 中的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)，任务就是克隆这个列表。

**示例：**

> **输入：** 列表 = [“极客”，“为”，“极客”]
> **输出：** 克隆列表 = [“极客”，“为”，“极客”]
>
> **输入：** 列表 = [“极客博客”、“计算机科学”、“门户”]
> **输出：** 克隆列表 = [“极客博客”、“计算机科学”、“门户”]

在 Java 中，有各种方法可以克隆列表。本文将解释实现相同的一些主要方法。

## Using a Copy Constructor

使用 Java 中的 `ArrayList` 构造函数，可以用另一个集合中的元素初始化一个新列表。

**语法：**

```java
ArrayList cloned = new ArrayList(collection c);
```

其中 `c` 是包含要添加到此列表的元素的集合。

**方法：**

1.  创建要克隆的列表。
2.  通过将原始列表作为 `ArrayList` 的复制构造函数的参数传递来克隆列表。

下面的代码演示了这个例子。

```java
// Program to clone a List in Java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class Example {
    public static void main(String[] args)
    {
        // Create a list
        List<String> original
            = Arrays.asList(
                "GeeksForGeeks",
                "A Computer Science",
                "Portal");

        // Clone the list
        List<String> cloned_list
            = new ArrayList<String>(original);

        System.out.println(cloned_list);
    }
}
```

**输出：**

```java
[GeeksForGeeks, A Computer Science, Portal]
```

## Using the addAll() method

`List` 类有一个名为 `addAll()` 的方法，它将一个集合的所有元素追加到列表中。

**语法：**

```java
boolean addAll(Collection c);
```

其中 `c` 是包含要添加到此列表的元素的集合。

**方法：**

1.  创建要克隆的列表。
2.  使用 `ArrayList` 构造函数创建一个空列表。
3.  使用 `addAll()` 方法将原始列表追加到空列表中。

下面的例子将说明这种方法。

```java
// Program to clone a List in Java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class Example {
    public static void main(String[] args)
    {
        // Create a list
        List<String> original
            = Arrays.asList(
                "GeeksForGeeks",
                "A Computer Science",
                "Portal");

        List<String> cloned_list
            = new ArrayList<String>();

        // Cloning a list
        cloned_list.addAll(original);

        System.out.println(cloned_list);
    }
}
```

**输出：**

```java
[GeeksForGeeks, A Computer Science, Portal]
```

## Using streams in Java 8

使用 [Java 8 中引入的 Streams API](https://www.geeksforgeeks.org/stream-in-java/)，可以克隆列表。`collect()` 方法（与 [`toList()`](https://www.geeksforgeeks.org/collectors-tolist-method-in-java-with-examples/) 方法一起）用于克隆列表。

**方法：**

1.  创建一个类。
2.  使用 `asList` 方法从数组创建类对象列表。
3.  使用 `stream()` 方法将对象列表转换为对象流。
4.  使用 `collect(Collectors.toList())` 方法收集所有流元素到列表实例，并将它们返回到克隆列表。

下面的程序说明了这个概念。

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

// Program to clone a List in Java
class Example {
    public static void main(String[] args)
    {
        // Create a list
        List<String> original
            = Arrays.asList(
                "GeeksForGeeks",
                "A Computer Science",
                "Portal");

        // Clone a list
        List<String> cloned_list
            = original.stream()
                  .collect(Collectors.toList());

        System.out.println(cloned_list);
    }
}
```

**输出：**

```java
[GeeksForGeeks, A Computer Science, Portal]
```

## Using the clone() method

Java 中类的 [`clone()` 方法](https://www.geeksforgeeks.org/clone-method-in-java-2/) 用于创建当前对象类的新实例，并用指定对象的内容初始化其所有字段。要克隆一个列表，可以遍历原始列表，使用 `clone` 方法复制所有列表元素，并使用 `add` 方法将它们追加到列表中。

**语法：**

```java
protected Object clone()
throws CloneNotSupportedException
```

**方法：**

1.  创建一个可克隆的类，该类覆盖了 `clone` 方法。
2.  使用 `asList` 方法从数组创建类对象列表。
3.  创建一个空列表。
4.  循环遍历原始列表的每个元素，调用类对象的 `clone()` 方法（返回类实例），并使用 `add()` 方法将其追加到新列表中。

下面的例子说明了这个概念。

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

// Class needs to be cloneable
class GfG implements Cloneable {

    String username;
    String msg;

    // Constructor
    GfG(String username, String msg)
    {
        this.username = username;
        this.msg = msg;
    }

    // To print the objects in the desired format
    @Override
    public String toString()
    {
        return "\nHello " + username + " !\n" + msg + "\n";
    }

    // Overriding the inbuilt clone class
    @Override
    protected GfG clone()
    {
        return new GfG(username, msg);
    }
}

// Program to clone a List in Java
class Example {
    public static void main(String[] args)
    {
        // Creating a list
        List<GfG> original
            = Arrays.asList(
                new GfG("Geeks",
                        "GeeksForGeeks"),
                new GfG("GFG",
                        "A computer science portal for geeks"));

        // Creating an empty list
        List<GfG> cloned_list
            = new ArrayList<GfG>();

        // Looping through the list
        // and cloning each element
        for (GfG temp : original)
            cloned_list.add(temp.clone());
        System.out.println(cloned_list);
    }
}
```

**输出：**

```java
[
Hello Geeks !
GeeksForGeeks, 
Hello GFG !
A computer science portal for geeks
]
```

## 使用 Apache Commons Lang

同样也可以通过使用 Apache Commons Lang 等第三方库提供的克隆方法来实现。

**语法：**

```java
public static <T> T clone(T object)
```

其中 `T` 是对象的类型，`object` 是要克隆的 `Serializable` 对象。

**方法：**

1.  创建一个可序列化的类。
2.  使用 `asList` 方法从数组创建类对象列表。
3.  创建一个空列表。
4.  循环遍历原始列表的每个元素，调用 `SerializationUtils.clone()` 方法（该方法返回类实例），并使用 `add()` 方法将其追加到新列表中。

下面的程序说明了这种情况。

```java
import org.apache.commons.lang3.SerializationUtils;
import java.io.Serializable;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

// Class should be Serializable
class GfG implements Serializable {
    String username;
    String msg;

    // Constructor
    GfG(String username, String msg)
    {
        this.username = username;
        this.msg = msg;
    }

    // Overriding to print the objects
    // in the desired manner
    @Override
    public String toString()
    {
        return "\nHello " + username
            + " !\n" + msg + "\n";
    }
}

// Program to clone a List in Java
class Example {
    public static void main(String[] args)
    {
        // Creating the list
        List<GfG> original
            = Arrays.asList(
                new GfG("Mukkesh",
                        "Hey there fellows!"),
                new GfG("McKenzie",
                        "Welcome to my page!"));

        // Creating an empty list
        List<GfG> cloned_list = new ArrayList<GfG>();

        // Looping through the list
        // and cloning each element
        // using SerializationUtils.clone
        for (GfG temp : original)
            cloned_list.add(
                SerializationUtils.clone(temp));
        System.out.println(cloned_list);
    }
}
```

**输出：**

```java
[
Hello Mukkesh !
Hey there fellows!, 
Hello McKenzie !
Welcome to my page!
]
```

## 使用 Gson 库将列表转换为 JSON
使用 Google 的 Gson 库，可以将列表转换为 JSON。此 JSON 字符串可以转换为 `List` 类型的对象，并用于初始化新的列表。

### 语法
```java
String gson.toJson(List a);
// 返回列表对象 `a` 的 JSON 字符串。

List gson.fromJson(String b, Class T)
// 从 JSON 字符串 `b` 返回类型为 `Class T` 的列表。
```

### 步骤
1.  创建一个类。
2.  使用 `asList` 方法从数组创建类对象列表。
3.  使用 `toJson()` 函数创建原始列表的 JSON 字符串，方法是将该字符串作为参数传递给该函数。
4.  存储返回的 JSON 字符串。
5.  创建一个空列表，通过使用 `fromJson()` 函数并将存储的 JSON 字符串作为参数传递，直接将其初始化为原始列表的值。

下面的程序说明了这一点。
```java
import com.google.gson.Gson;
import java.io.Serializable;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

// Class should be Serializable
class GfG implements Serializable {
    String username;
    String msg;

    // Constructor
    GfG(String username, String msg) {
        this.username = username;
        this.msg = msg;
    }

    // Overriding to print the object
    // in the desired format
    @Override
    public String toString() {
        return "\nHello " + username + " !\n" + msg + "\n";
    }
}

// Program to clone a List in Java
class Example {
    public static void main(String[] args) {
        // Creating a new list
        List<GfG> original
            = Arrays.asList(new GfG("Mukkesh",
                                    "Hey there fellows!"),
                            new GfG("McKenzie",
                                    "Welcome to my page!"));
        // Creating a gson object
        Gson gson = new Gson();

        // Converting the list into a json string
        String jsonstring
            = gson.toJson(original);

        // Converting the json string
        // back into a list
        List<GfG> cloned_list
            = gson.fromJson(jsonstring, GfG.class);

        System.out.println(cloned_list);
    }
}
```

### 输出
```java
[
Hello Mukkesh !
Hey there fellows!, 
Hello McKenzie !
Welcome to my page!
]
```

## 使用反射包
[反射包](https://www.geeksforgeeks.org/reflection-in-java/) 也可以用来克隆列表。

### 步骤
1.  创建一个可克隆的类，该类覆盖了 `clone` 方法。
2.  使用 `asList` 方法从数组创建类对象列表。
3.  创建一个空列表。
4.  使用 `getClass().getDeclaredMethod("clone")` 方法从类中获取克隆方法（在列表的一个元素上），并将其存储为 `Method` 实例。
5.  循环遍历列表的每个元素，并调用存储的方法，该方法将返回一个类实例，该实例可以追加到新列表中。

```java
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

// GfGclass implements Cloneable Interface
class GfG implements Cloneable {
    String username;
    String msg;

    // Constructor
    GfG(String username, String msg) {
        this.username = username;
        this.msg = msg;
    }

    // Overriding to print the object
    // in the desired format
    @Override
    public String toString() {
        return "\nHello " + username
            + "!\n" + msg + "\n";
    }

    // Overriding the clone function
    @Override
    protected Object clone()
        throws CloneNotSupportedException {
        return new GfG(username, msg);
    }
}

class ListUtils {
    // Create a cloning function
    public static <T extends Cloneable> List<T>
    clone(List<T> original)
        throws NoSuchMethodException,
               InvocationTargetException,
               IllegalAccessException {

        // Boundary conditions checked
        if (original == null
            || original.size() == 0) {
            return new ArrayList<>();
        }

        // Get the clone method from the GfG class
        Method method
            = original.get(0)
                  .getClass()
                  .getDeclaredMethod("clone");

        // Create an empty list for cloning
        List<T> clone = new ArrayList<>();

        // Loop through the list and
        // invoke the clone method of each element
        for (T item : original) {
            clone.add((T)method.invoke(item));
        }

        // Return the cloned list
        return clone;
    }

    public static void main(String[] args) {
        // Creating a list
        List<GfG> original
            = Arrays.asList(
                new GfG("Geeks",
                        "GeeksForGeeks"),
                new GfG("GFG",
                        "A computer science portal for geeks"));

        // Create an empty list for cloning
        List<GfG> cloned_list = null;

        // Use try and catch for exception handling
        try {
            cloned_list = clone(original);
        }
        catch (NoSuchMethodException e) {
            e.printStackTrace();
        }
        catch (InvocationTargetException e) {
            e.printStackTrace();
        }
        catch (IllegalAccessException e) {
            e.printStackTrace();
        }

        // Print the cloned list
        System.out.println(cloned_list);
    }
}
```

### 输出
```java
[
Hello Geeks!
GeeksForGeeks, 
Hello GFG!
A computer science portal for geeks
]
```