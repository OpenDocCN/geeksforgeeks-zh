# Java中的ManagementPermission类

> 原文：[`https://www.geeksforgeeks.org/java-lang-management-managementpermission-class-in-java/`](https://www.geeksforgeeks.org/java-lang-management-managementpermission-class-in-java/)

`java.lang.ManagementPermission`类包含确定对系统资源的访问的抽象方法。每个物体都有名字。大多数权限对象也有一些相关联的“动作”，告诉这个权限对象允许哪些活动。

## 类声明

```java
public final class ManagementPermission
extends BasicPermission
```

## 构造方法

```java
Permission(String name)
```

**`ManagementPermission(String name)`**：使用此名称构造新的权限对象。

## 方法

| 方法 | 描述 |
| --- | --- |
| `checkGuard(Object object)` | Used to determine whether the Permission object can be protected (protect access to another object). |
| `equals(Object object)` | Check whether two permission objects are equal. |
| `hashCode()` | It returns the hash value of this Permission object. |
| `getName()` | 返回该权限的名称。 |
| `implies(Permission permission)` | Check whether this ManagementPermssion object implies this permission. |
| `newPermissionCollection()` | It returns a new PermissionCollection object. |
| `toString()` | It returns the string representation of the specified Permission object. |

### 1. `public void checkGuard(Object object)`
用于判断该`Permission`对象是否可以被保护(保护对另一个对象的访问)。

```java
Parameters:
object - the object to guard.
Throws:
SecurityException - if the access is denied by checkPermission method.
```

### 2. `public abstract boolean implies(Permission permission)`
检查这个`ManagementPermssion`对象是否隐含这个权限。

```java
Parameters:
permission - the permission to check against.
Returns:
true if this permission is implied by this object, false otherwise.
```

### 3. `public abstract boolean equals(Object obj)`
检查两个`Permission`对象是否相等。

```java
Parameters:
obj - the object to be compared
Returns:
true if both Permission objects are equal, false otherwise.
```

### 4. `public abstract int hashCode()`
它返回这个`Permission`对象的哈希代码值。

```java
Returns:
a hash code value for this object.
```

### 5. `public final String getName()`
它返回此权限的名称。

```java
Returns:
the name of this Permission.
```

### 6. `public abstract String getActions()`
它以字符串格式返回此权限对象的操作。

```java
Returns:
the actions of this Permission.
```

### 7. `public PermissionCollection newPermissionCollection()`
返回一个新的`PermissionCollection`对象。

```java
Returns:
a new PermissionCollection object
```

### 8. `public String toString()`
它返回指定权限对象的字符串表示形式。

```java
Returns:
string representation of the specified Permission object.
```

## 示例代码

```java
import java.lang.management.ManagementPermission;
import java.security.Permission;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a new ManagementPermission object with
        // name control
        Permission p = new ManagementPermission("control");
        try {
            // Printing name of the object
            System.out.println("Name: " + p.getName());
            // Printing hash value of the object
            System.out.println("Hashcode: " + p.hashCode());
            // Printing actions of the object
            System.out.println("Actions: "
                               + p.getActions());
            // Converting this managementPermission object
            // to new PermissionCollection object
            System.out.println(
                "As a new PermissionCollection object: "
                + p.newPermissionCollection().toString());
            // Checking if new permissionCollection implies
            // managementPermission object or not
            System.out.println(
                "Implies: "
                + p.newPermissionCollection().implies(p));
        }
        catch (Exception e) {
            System.err.println(e.toString());
        }
    }
}
```

## 输出

```java
Name: control
Hashcode: 951543133
Actions: 
As a new PermissionCollection object: java.security.BasicPermissionCollection@5b6f7412 (
)

Implies: false
```