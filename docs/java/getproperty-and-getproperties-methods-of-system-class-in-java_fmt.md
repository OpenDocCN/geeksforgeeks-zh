# Java 中 `System` 类的 `getProperty()` 和 `getProperties()` 方法

> 原文：[https://www.geeksforgeeks.org/getproperty-and-getproperties-methods-of-system-class-in-java/](https://www.geeksforgeeks.org/getproperty-and-getproperties-methods-of-system-class-in-java/)

Java 中的 `System` 类有两种方法用于读取系统属性：

*   `getProperty`: `System` 类有两个不同版本的 `getProperty`。两者都检索参数列表中命名的属性值。两个 `getProperty` 方法中较简单的一个只接受一个参数。
*   `getProperties`: `java.lang.System.getProperties()` 方法决定当前的系统属性。

## 方法说明

*   `getProperty(String key)`: `java.lang.System.getProperty(String key)` 方法返回一个包含属性值的字符串。如果属性不存在，此版本的 `getProperty` 将返回 `null`。这基于下表中提到的键值对。

    **语法:**

    ```java
    public static String getProperty(String key)
    Parameters :
    key : key whose system property we want
    Returns :
    System property as specified the key
    Null : if there is no property present with that key.
    ```

*   **实施:**

    ```java
    // Java Program illustrating the working of getProperty(String key) method

    import java.lang.*;
    import java.util.Properties;

    public class NewClass
    {
        public static void main(String[] args)
        {
            // Printing Name of the system property
            System.out.println("user.dir: "+System.getProperty("user.dir"));

            // Fetches the property set with 'home' key
            System.out.println("home: "+System.getProperty("home"));
            // Resulting in Null as no property is present

            // Printing 'name of Operating System'
            System.out.println("os.name: "+System.getProperty("os.name"));

            // Printing 'JAVA Runtime version'
            System.out.println("version: "+System.getProperty("java.runtime.version" ));

            // Printing 'name' property
            System.out.println("name: "+System.getProperty("name" ));
            // Resulting in Null as no property is present
        }
    }
    ```

*   **输出:**

    ```java
    user.dir: /tmp/hsperfdata_bot
    home: null
    os.name: Linux
    version: 1.8.0_101-b13
    name: null
    ```

*   `getProperty(String key, String definition)`: `java.lang.System.getProperty(String key, String definition)` 允许设置参数 `definition`，即可以为特定键设置默认值。

    **语法:**

    ```java
    public static String getProperty(String key, String def)
    Parameters :
    key : system property
    def : default value of the key to be specified
    Returns :
    System Property
    Null : if there is no property present with that key.
    ```

*   **实施:**

    ```java
    // Java Program illustrating the working of
    // getProperty(String key, String definition) method
    import java.lang.*;
    import java.util.Properties;

    public class NewClass
    {
        public static void main(String[] args)
        {
            // use of getProperty(String key, String definition) method

            // Here key = "Hello" and System Property = "Geeks"
            System.out.println("Hello property : "
                            + System.getProperty("Hello", "Geeks"));

            // Here key = "Geek" and System Property = "For Geeks"
            System.out.println("System-property :"
                            + System.getProperty("System", "For Geeks"));

            // Here key = "Property" and System Property = null
            System.out.println("Property-property :"
                            + System.getProperty("Property"));

        }
    }
    ```

*   **输出:**

    ```java
    Hello key property : Geeks
    System key property :For Geeks
    Property key property :null
    ```

*   `getProperties()`: `java.lang.System.getProperties()` 获取系统上的 JVM 从操作系统获取的当前属性。当前系统属性作为 `Properties` 对象返回，供 `getProperties()` 方法使用。如果不存在这样的属性集，则首先创建一组系统属性，然后对其进行初始化。还可以使用 `System.setProperties()` 方法修改现有的一组系统属性。属性文件中有多个键值对，部分如下：

    ```java
    Keys                         Values

    -->  os.version              :  OS Version
    -->  os.name                 :  OS Name
    -->  os.arch                 :  OS Architecture
    -->  java.compiler           :  Name of the compiler you are using
    -->  java.ext.dirs           :  Extension directory path
    -->  java.library.path       :  Paths to search libraries whenever loading
    -->  path.separator          :  Path separator
    -->  file.separator          :  File separator
    -->  user.dir                :  Current working directory of User
    -->  user.name               :  Account name of User
    -->  java.vm.version         :  JVM implementation version
    -->  java.vm.name            :  JVM implementation name
    -->  java.home               :  Java installation directory
    -->  java.runtime.version    :  JVM version
    ```

    **语法:**

    ```java
    public static Properties getProperties()
    Parameters :

    Returns :
    System properties that JVM gets on your System gets from OS
    ```

*   **实施:**

    ```java
    // Java Program illustrating the working of getProperties() method

    import java.lang.*;
    import java.util.Properties;

    public class NewClass
    {
        public static void main(String[] args)
        {

            /* Use of getProperties() method
               System class refers to the JVM on which you are compiling your JAVA code
               getProperty fetches the actual properties
               that JVM on your Sysytem gets from your Operating System
            */

            System.out.println("Following are the JVM information of your OS :");
            System.out.println("");

            // Property Object
            Properties jvm = System.getProperties();
            jvm.list(System.out);
        }
    }
    ```

*   输出：点击[此处](https://ide.geeksforgeeks.org/U9ehOC)查看输出

## 要点

*   `java.lang.System.getProperty(String key)`: 只获取那些属性–您将使用键指定的值(与您想要的特定值相关联)。
*   `java.lang.System.getProperty(String key, String definition)`: 帮助您创建自己想要的键值集。
*   `java.lang.System.getProperties()`: 获取所有属性–系统上的 JVM 从操作系统获取的值。

本文由 **莫希特·古普塔供稿🙂** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。