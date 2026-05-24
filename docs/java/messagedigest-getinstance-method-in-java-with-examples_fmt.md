# Java 中的 MessageDigest getInstance()方法，带示例

> 原文：[https://www.geeksforgeeks.org/messagedigest-getinstance-method-in-java-with-examples/](https://www.geeksforgeeks.org/messagedigest-getinstance-method-in-java-with-examples/)

## getInstance(String algorithm)

`java.security.MessageDigest`类的`getInstance()`方法，用于返回一个`MessageDigest`类型的对象，该对象应用分配的`MessageDigest`算法。

**语法：**

```java
public static MessageDigest
  getInstance(String algorithm)
  throws NoSuchAlgorithmException
```

**参数：** 该方法接受`标准算法`的名称作为参数。

**返回值：** 该方法提供一个类型为`MessageDigest`的对象。

**异常：** 如果没有提供程序支持特定算法的消息摘要spi应用程序，此方法将引发以下异常：

*   `NoSuchAlgorithmException`：如果算法不可用。
*   `NullPointerException`：如果算法为`null`。

以下是说明`getInstance()`方法的示例：

**例 1：**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance("MD5");

            // getting the status of MessageDigest object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Status : MD5 Message Digest from SUN, <initialized>
```

**示例 2：** 显示`NoSuchAlgorithmException`异常

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance("GFG");

            // getting the status of MessageDigest object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Exception thrown :
 java.security.NoSuchAlgorithmException:
 GFG MessageDigest not available
```

## getInstance(String algorithm, String provider)

`java.security.MessageDigest`类的`getInstance()`方法提供了一个`MessageDigest`类型的对象，该对象应用分配的`MessageDigest`算法和分配的提供程序对象。

**语法：**

```java
public static MessageDigest 
  getInstance(String algorithm, String provider)
  throws NoSuchAlgorithmException
```

**参数：** 此方法寻求以下参数作为参数：

*   `Algorithm`：这是要在此实例中指定的算法的名称。
*   `Provider`：这是指定的提供者的名称。

**返回值：** 该方法提供一个类型为`MessageDigest`的对象。

**异常：** 此方法引发以下异常：

*   `NoSuchAlgorithmException`：如果特定提供者没有特定算法的消息摘要Spi实现。
*   `IllegalArgumentException`：如果提供者名称为`null`。
*   `NullPointerException`：如果算法为`null`。

以下是说明`getInstance()`方法的示例：

**例 1：**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance(
                    "SHA-384", "SUN");

            // getting the status of MessageDigest object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Status : SHA-384 Message Digest from SUN, <initialized>
```

**示例 2：** 显示`NoSuchAlgorithmException`异常

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance(
                    "GFG", "SUN");

            // getting the status of MessageDigest object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Exception thrown :
 java.security.NoSuchAlgorithmException:
 no such algorithm: GFG for provider SUN
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#getInstance-java.lang.String-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#getInstance-java.lang.String-java.lang.String-)