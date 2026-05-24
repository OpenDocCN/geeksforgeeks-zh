# Java 中的 `java.lang.reflect.ReflectPermission` 类

> 原文：[https://www.geeksforgeeks.org/java-lang-reflect-reflectpermission-class-in-java/](https://www.geeksforgeeks.org/java-lang-reflect-reflectpermission-class-in-java/)

`ReflectPermission` 类扩展了 `BasicPermission` 类。这是一个“命名”权限，即它包含一个名称，但不包含任何操作。如果需要，它可以在基本权限之上实现操作。它用于获取关于构造函数行为的信息。

| **构造函数** | **描述** |
| --- | --- |
| `ReflectPermission(String name)` | 用于创建具有指定名称的反射权限。 |
| `ReflectPermission(String name, String action)` | 用于创建具有指定名称和操作的反射权限。 |

**继承自 `java.security.BasicPermission` 类的方法：**

| **方法** | **描述** |
| --- | --- |
| `equals(Object obj)` | 检查两个 `BasicPermission` 对象是否相等。 |
| `getClass()` | 以字符串格式返回操作，由于 `ReflectPermission` 中没有操作，当前为空字符串。 |
| `hashCode()` | 返回此对象的哈希码值。 |
| `implies(Permission perm)` | 检查给定的权限是否由此对象隐含。 |
| `newPermissionCollection()` | 返回一个新的 `PermissionCollection` 对象。 |

下面是给定类的示例/用法：

## 示例

```java
// Use of java.lang.reflect.ReflectPermission Class in Java
import java.lang.reflect.ReflectPermission;
class GFG {
    public static void main(String[] args)
    {
        if (canAccessPrivateMethods()) {
            System.out.println("Permission granted");
        }
        else {
            System.out.println("Permission not granted");
        }
    }
    static boolean canAccessPrivateMethods()
    {
        try {
            SecurityManager securityManager
                = System.getSecurityManager();
            if (null != securityManager) {
                securityManager.checkPermission(
                    new ReflectPermission(
                        "suppressAccessChecks"));
            }
        }
        catch (SecurityException e) {
            return false;
        }
        return true;
    }
}
```

**输出**

```
Permission not granted
```