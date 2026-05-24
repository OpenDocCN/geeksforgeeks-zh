# java 中的 java.net.SocketPermission 类

> 原文: [https://www.geeksforgeeks.org/java-net-socketpermission-class-in-java/](https://www.geeksforgeeks.org/java-net-socketpermission-class-in-java/)

`java.net.SocketPermission` 类表示您是否有权通过套接字访问网络。`SocketPermission` 由一个主机和一组操作组成。

## 类声明

```java
public final class SocketPermission
extends Permission
implements Serializable
```

## 构造函数

| 构造函数 | 描述 |
| --- | --- |
| `SocketPermission(String name)` | 这将构造一个具有指定名称的管理权限。 |
| `SocketPermission(String host, String actions)` | 这将构造一个新的管理权限对象。 |

## `SocketPermission(String host, String actions)`

用于创建具有指定操作的 `SocketPermission` 类的新对象。

## 方法

| 方法 | 描述 |
| --- | --- |
| `equals(Object obj)` | 它检查两个 `SocketPermission` 对象是否相等。 |
| `getActions()` | 它以字符串格式返回此 `SocketPermission` 对象的操作。 |
| `hashCode()` | 返回此 `SocketPermission` 对象的哈希码值。 |
| `implies(Permission p)` | 检查此 `SocketPermission` 对象是否隐含此权限。 |
| `newPermissionCollection()` | 它返回一个新的 `PermissionCollection` 对象。 |

## 示例

### Java

```java
// Java Program to show the usage of
// java.net.SocketPermission Class
import java.io.IOException;
import java.net.SocketPermission;
import java.security.Permission;
import java.security.PermissionCollection;

public class Socket {

    public static void main(String args[]) {
        try {
            // getting permission object
            Permission p = getPermission();

            // print actions of permission p
            System.out.println(p.getActions());

            // printing hashcode value of permission p
            System.out.println(p.hashCode());

            // creating a permissionCollection object and
            // printing it
            PermissionCollection p1 = p.newPermissionCollection();
            System.out.print(p1);
        } catch (Exception e) {
            System.err.print("Permission denied");
        }
    }

    public static Permission getPermission() throws IOException {
        int port = 3000;
        String host = "localhost";
        return new SocketPermission(host + ":" + port, "Connect,resolve");
    }
}
```

## 输出

```java
connect,resolve

java.net.SocketPermissionCollection@30dae81 (
)
```