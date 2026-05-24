# 使用JavaTuples

## 在Java中用三元组类实现四重奏类

> 原文：`https://www.geeksforgeeks.org/implement-quartet-class-with-triplet-class-in-java-using-java-tuples/`

### 以下是用`Triplet`实现`Quartet`的方法

#### 1. 直接使用值

```java
import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Create Quartet from Triplet
        Quartet<String, String, String, String>
            quartet = new Quartet<String, String, String, String>(
                "Quartet 1",
                triplet.getValue0(),
                triplet.getValue1(),
                triplet.getValue2());

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
[Triplet 1, 1, GeeksforGeeks]
[Quartet 1, Triplet 1, 1, GeeksforGeeks]
```

#### 2. 使用`Triplet.add()`方法

```java
import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Using add() to create Quartet
        Quartet<String, String, String, String>
            quartet = triplet.add("Quartet 1");

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
Triplet: [Triplet 1, 1, GeeksforGeeks]
Quartet: [Triplet 1, 1, GeeksforGeeks, Quartet 1]
```

#### 3. 使用`Triplet.addAtX()`方法

##### 程序 1：使用`addAt0()`在位置 0 添加

```java
// Below is a Java program to demonstrate
// use of addAt0() method with
// direct value

import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        /// create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Using addAt0() to create Quartet
        Quartet<String, String, String, String>
            quartet = triplet.addAt0("Quartet 1");

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
Triplet: [Triplet 1, 1, GeeksforGeeks]
Quartet: [Quartet 1, Triplet 1, 1, GeeksforGeeks]
```

##### 程序 2：使用`addAt1()`在位置 1 添加

```java
// Below is a Java program to demonstrate
// use of addAt1() method with
// direct value

import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Using addAt1() to create Quartet
        Quartet<String, String, String, String>
            quartet = triplet.addAt1("Quartet 1");

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
Triplet: [Triplet 1, 1, GeeksforGeeks]
Quartet: [Triplet 1, Quartet 1, 1, GeeksforGeeks]
```

##### 程序 3：使用`addAt2()`在位置 2 添加

```java
// Below is a Java program to demonstrate
// use of addAt2() method with
// direct value

import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Using addAt2() to create Quartet
        Quartet<String, String, String, String>
            quartet = triplet.addAt2("Quartet 1");

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
Triplet: [Triplet 1, 1, GeeksforGeeks]
Quartet: [Triplet 1, 1, Quartet 1, GeeksforGeeks]
```

##### 程序 4：使用`addAt3()`在位置 3 添加

```java
// Below is a Java program to demonstrate
// use of addAt3() method with
// direct value

import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // create Triplet
        Triplet<String, String, String>
            triplet = new Triplet<String, String, String>(
                "Triplet 1", "1", "GeeksforGeeks");

        // Print Triplet
        System.out.println("Triplet: " + triplet);

        // Using addAt3() to create Quartet
        Quartet<String, String, String, String>
            quartet = triplet.addAt3("Quartet 1");

        // Print Quartet
        System.out.println("Quartet: " + quartet);
    }
}
```

**输出：**

```java
Triplet: [Triplet 1, 1, GeeksforGeeks]
Quartet: [Triplet 1, 1, GeeksforGeeks, Quartet 1]
```