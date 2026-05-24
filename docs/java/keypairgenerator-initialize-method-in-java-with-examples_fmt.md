# Java 中的 KeyPairGenerator initialize() 方法示例

> 原文：[https://www.geeksforgeeks.org/keypairgenerator-initialize-method-in-java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-initialize-method-in-java-with-examples/)

## `initialize(int keysize)`

`java.security.KeyPairGenerator` 的 `initialize()` 方法用于初始化 `KeyPairGenerator` 对象以备后用。

**语法：**
```java
public void initialize(int keysize)
```

**参数：** 该方法寻求 `int` 类型的 `keysize` 作为参数。
**返回值：** 这个方法没有返回值。
**异常：** 如果传入的值大于或小于指定标准，该方法抛出 `InvalidParameterException`。

**注意：** 以下程序不会在在线 IDE 上运行。

以下是说明 `initialize(int keysize)` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
Keypair : java.security.KeyPair@12a3a380
```

### 示例 2：对于 `InvalidParameterException`

```java
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // initializing with 1024
            kpg.initialize(-24);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
Exception thrown :
 java.security.InvalidParameterException:
 RSA keys must be at least 512 bits long
```

## `initialize(int keysize, SecureRandom random)`

`java.security.KeyPairGenerator` 的 `initialize()` 方法使用 `SecureRandom` 对象将 `KeyPairGenerator` 初始化为特定大小，以便进一步使用。

**语法：**
```java
public void initialize(int keysize,
                       SecureRandom random)
```

**参数：** 该方法采用以下参数：
*   `keysize`：即密钥尺寸。
*   `random`：`SecureRandom` 类型的对象。

**返回值：** 该方法返回 `KeyPairGenerator` 的对象。
**异常：** 如果传入的值大于或小于指定标准，该方法抛出 `InvalidParameterException`。

以下是说明 `initialize()` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // creating the object of SecureRandom
            SecureRandom se
                = SecureRandom.getInstance("SHA1PRNG");

            // initializing with 1024
            kpg.initialize(1024, se);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
Keypair : java.security.KeyPair@4e25154f
```

### 示例 2：对于 `InvalidParameterException`

```java
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // creating the object of SecureRandom
            SecureRandom se
                = SecureRandom.getInstance("SHA1PRNG");

            // initializing with -24
            kpg.initialize(-24, se);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**
```java
Exception thrown :
 java.security.InvalidParameterException:
 RSA keys must be at least 512 bits long
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/security/KeyPairGenerator.html#initialize-int-java.security.SecureRandom-](https://docs.oracle.com/javase/9/docs/api/java/security/KeyPairGenerator.html#initialize-int-java.security.SecureRandom-)