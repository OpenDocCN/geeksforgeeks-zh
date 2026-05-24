# Java 中的算法参数生成器 `getInstance()` 方法，带示例

> 原文: [https://www.geeksforgeeks.org/algorithmparametergenerator-getinstance-method-in-java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-getinstance-method-in-java-with-examples/)

## 字符串算法

`AlgorithmParameterGenerator` 类的 `getInstance()` 方法用于返回实现指定算法的 `AlgorithmParameterGenerator` 类型的对象。

### 语法:

```java
public static AlgorithmParameterGenerator getInstance(String algorithm) throws NoSuchAlgorithmException
```

### 参数:
该方法以算法的 `标准名称` 为参数。

### 返回值:
该方法返回 `新算法参数生成器对象`。

### 异常:
此方法抛出以下异常:
*   `NoSuchAlgorithmException`: 如果没有提供程序支持指定算法的算法参数生成器或 PI 实现。
*   `NullPointerException`: 如果指定的算法为空。

以下是举例说明 `getInstance()` 方法:

### 例 1:

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // Getting instance of
            // AlgorithmParameterGenerator
            // By using getInstance() method
            AlgorithmParameterGenerator sr
                = AlgorithmParameterGenerator
                      .getInstance("DSA");

            // getting the status of
            // AlgorithmParameterGenerator object
            String str = sr.toString();

            // printing the status
            System.out.println("Status: "
                               + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

### 输出:

```java
Status: java.security.AlgorithmParameterGenerator@232204a1
```