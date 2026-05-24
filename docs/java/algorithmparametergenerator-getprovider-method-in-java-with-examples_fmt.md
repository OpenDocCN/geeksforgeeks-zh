# Java 中的算法参数生成器 `getProvider()` 方法示例

> 原文：[https://www.geeksforgeeks.org/algorithmparametergenerator-getprovider-method-in-java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-getprovider-method-in-java-with-examples/)

`java.security.AlgorithmParameterGenerator` 类的 `getProvider()` 方法用于返回该算法参数生成器对象的提供者。

**语法：**

```java
public final Provider getProvider()
```

**返回值：** 这个方法返回这个算法参数生成器对象的提供者。

以下是说明 `getProvider()` 方法的示例：

**示例 1：** 对于算法 `DSA`

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
            // AlgorithmParameterGenerator
            // and getting instance
            // using getInstance() method
            AlgorithmParameterGenerator
                sr
                = AlgorithmParameterGenerator
                      .getInstance("DSA");

            // initializing the AlgorithmParameterGenerator
            // with 1024 using initialize() method
            sr.init(1024);

            // generating the Parameters
            // using getAlgorithm() method
            Provider pro = sr.getProvider();

            // printing the string algo
            System.out.println("Provider : " + pro);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Provider : SUN version 1.8
```

**示例 2：** 对于算法 `DiffieHellman`

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
            // AlgorithmParameterGenerator
            // and getting instance
            // using getInstance() method
            AlgorithmParameterGenerator
                sr
                = AlgorithmParameterGenerator
                      .getInstance("DiffieHellman");

            // initializing the AlgorithmParameterGenerator
            // with 1024 using initialize() method
            sr.init(1024);

            // generating the Parameters
            // using getAlgorithm() method
            Provider pro = sr.getProvider();

            // printing the string algo
            System.out.println("Provider : " + pro);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Provider : SunJCE version 1.8
```