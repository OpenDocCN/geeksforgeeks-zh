# Java中的`DigestOutputStream.setMessageDigest()`方法，带示例

> 原文：[https://www.geeksforgeeks.org/digestoutputstream-setmessagedigest-method-in-java-with-examples/](https://www.geeksforgeeks.org/digestoutputstream-setmessagedigest-method-in-java-with-examples/)

`java.security.DigestOutputStream`类的`setMessageDigest()`方法，用于将指定的消息摘要分配给`DigestOutputStream`对象。

## 语法

```java
public void setMessageDigest(MessageDigest digest)
```

## 返回值
这个方法没有什么可返回的。

## 注意
本文中的所有程序都不会在在线IDE上运行，因为不存在“`name`”文件。您可以在系统的Java编译器上检查这些代码。要检查此代码，请在您的系统上创建一个文件“`name`”。

以下是举例说明`setMessageDigest()`方法：

### 例1：Java语言

```java
// Java program to demonstrate
// setMessageDigest() method

import java.security.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance("MD5");

            // creating and initializing
            // object of OutputStream
            OutputStream is
                = new FileOutputStream(
                    "f:/java/name.txt");

            // creating and initializing
            // object of DigestOutputStream
            DigestOutputStream di
                = new DigestOutputStream(is, sr);

            // display the result
            System.out.println("MessageDigest before assigning : "
                               + di.getMessageDigest());

            // assigning the MessageDigest to this stream
            // using setMessageDigest() method
            di.setMessageDigest(
                MessageDigest.getInstance("SHA-1"));

            // display the result
            System.out.println("MessageDigest after assigning : "
                               + di.getMessageDigest());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (FileNotFoundException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

## 输出

```java
MessageDigest before assigning : MD5 Message Digest from SUN,

MessageDigest after assigning : SHA-1 Message Digest from SUN, 
```