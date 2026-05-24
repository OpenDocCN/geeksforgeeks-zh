# Java RMI Naming 类

> 原文：[https://www.geeksforgeeks.org/java-rmi-naming-class-in-java/](https://www.geeksforgeeks.org/java-rmi-naming-class-in-java/)

`java.rmi.Naming` 类提供了一组方法，用于在远程注册表中绑定、解绑、重绑定远程对象名称，或获取远程对象的引用及列出所有绑定名称。

## 类声明

```java
public final class Naming extends Object
```

## 主要方法

`Naming` 类最常用的方法如下：

1.  `bind()`
2.  `list()`
3.  `lookup()`
4.  `rebind()`
5.  `unbind()`

### 方法 1：`bind()`

**语法：**

```java
static void bind(String name, Remote object)
// Bind this name with this remote object
```

**参数：** 远程注册表的名称。

**异常：**

1.  `AlreadyBoundException` - 当名称已被绑定时抛出。
2.  `MalformedURLException` - 当名称的格式不是有效的 URL 时抛出。
3.  `RemoteException` - 当与远程注册表联系失败时抛出。
4.  `AccessException` - 当不允许访问此操作时抛出。

### 方法 2：`list()`

用于获取与注册表关联的名称列表。

**语法：**

```java
static String[] list(String name)
```

**参数：** 远程注册表的名称。

**返回类型：** 与此注册表绑定的名称数组。

**异常：**

1.  `MalformedURLException` - 当名称的格式不是有效的 URL 时抛出。
2.  `RemoteException` - 当与远程注册表联系失败时抛出。

### 方法 3：`lookup()`

查找与该名称关联的远程对象的引用。

**语法：**

```java
static Remote lookup(String name)
```

**参数：** 远程注册表的名称。

**返回类型：** 远程对象的引用。

**异常：**

1.  `NotBoundException` - 当名称未绑定到当前操作时抛出。
2.  `RemoteException` - 当与远程注册表联系失败时抛出。
3.  `AccessException` - 当不允许访问此操作时抛出。
4.  `MalformedURLException` - 当名称的格式不是有效的 URL 时抛出。

### 方法 4：`rebind()`

将此名称与关联的远程对象重新绑定。

**语法：**

```java
static void rebind(String name, Remote object)
```

**参数：** 接受两个参数，即名称和对象。
*   远程注册表的名称。
*   要关联的远程对象。

**异常：**

1.  `MalformedURLException` - 当名称的格式不是有效的 URL 时抛出。
2.  `RemoteException` - 当与远程注册表联系失败时抛出。
3.  `AccessException` - 当不允许访问此操作时抛出。

### 方法 5：`unbind()`

解除此名称与关联远程对象的绑定。

**语法：**

```java
static void unbind(String name)
```

**参数：** 远程注册表的名称。

**异常：**

1.  `NotBoundException` - 当名称未绑定到当前操作时抛出。
2.  `MalformedURLException` - 当名称的格式不是有效的 URL 时抛出。
3.  `RemoteException` - 当与远程注册表联系失败时抛出。
4.  `AccessException` - 当不允许访问此操作时抛出。

## 示例

### 示例 1：创建注册表（服务器端）

```java
// Java Program to create a registry
// Server's Side

// Importing java.rmi package to enable object of one JVM
// to invoke methods on object in another JVM
import java.rmi.*;
import java.rmi.AlreadyBoundException;
import java.rmi.Naming;
import java.rmi.NotBoundException;
import java.rmi.Remote;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.*;

// Interface
// creating remote interface
interface demo extends Remote {
    public String msg(String msg) throws RemoteException;
}

// Class 1
// Helper Class
class demoRemote
    extends UnicastRemoteObject implements demo {
    demoRemote() throws RemoteException { super(); }

// @Override
    public String msg(String msg) throws RemoteException
    {
        // Display message only
        System.out.println("GeeksForGeeks");
        return null;
    }
}

// Class 2
// Main class
public class GFG_Server {

// Main driver method
    public static void main(String args[])
        throws RemoteException, NotBoundException,
               AlreadyBoundException
    {

// Try block to check for exceptions
        try {

// Creating a new registry by creating
            // an object of Registry class
            Registry registry
                = LocateRegistry.createRegistry(3000);

demo obj = new demoRemote();

// binding obj to remote registry
            Naming.bind("rmi://localhost:3000"
                            + "/geeksforgeeks",
                        (Remote)obj);

// Display message when program
            // is executed succussfully
            System.out.println(
                "registry created successfully");
        }

// Catch block to handle the exceptions
        catch (Exception e) {

// Getting the name of the exception using
            // the toString() method over exception object
            System.err.println(e.toString());
        }
    }
}
```

**输出：**

```
registry created successfully
```

### 示例 2：查找对象（客户端）

```java
// Java Program to look for the object
// Client Side

// Importing java.rmi package to enable object of one JVM
// to invoke methods on object in another JVM
import java.rmi.*;

// Main class
public class GFG_Client {

// Main driver method
    public static void main(String args[])
    {
        // try block to check for exceptions
        try {

// Looking for object in remote registry
            demo client = (demo)Naming.lookup(
                "rmi://localhost:3000/obj");

// Print and display the client message
            System.out.println(client.msg());
        }

// Catch block to handle the exception
        catch (Exception e) {
        }
    }
}
```

**输出：**

```
GeeksForGeeks
```