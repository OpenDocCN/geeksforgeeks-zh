# Java 中的 `AlgorithmParameters` 类的 `getAlgorithm()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/algorithmparameters-getalgorithm-method-in-java-with-examples/](https://www.geeksforgeeks.org/algorithmparameters-getalgorithm-method-in-java-with-examples/)

`java.security.AlgorithmParameters` 类的 `getAlgorithm()` 方法用于返回与此参数生成器关联的算法的标准名称。

**语法：**

```java
public final String getAlgorithm()
```

**返回值：** 该方法返回算法的字符串名称。

以下是说明 `getAlgorithm()` 方法的示例：

**示例 1：** 对于算法 `DSA`

## 示例 1

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // AlgorithmParameters
            // and getting instance
            // using getInstance() method
            AlgorithmParameters sr
                = AlgorithmParameters
                      .getInstance("DSA");

            // generating the Parameters
            // using getAlgorithm() method
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm: "
                               + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output：**

```java
Algorithm: DSA
```

**示例 2：** 对于算法 `DiffieHellman`

## 示例 2

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // AlgorithmParameters
            // and getting instance
            // using getInstance() method
            AlgorithmParameters sr
                = AlgorithmParameters
                      .getInstance("DiffieHellman");

            // generating the Parameters
            // using getAlgorithm() method
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm: "
                               + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output：**

```java
Algorithm: DiffieHellman
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/security/AlgorithmParameters.html#getAlgorithm--](https://docs.oracle.com/javase/9/docs/api/java/security/AlgorithmParameters.html#getAlgorithm--)