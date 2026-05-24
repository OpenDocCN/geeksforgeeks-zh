# C# | Char。等于()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-char-equals-method/](https://www.geeksforgeeks.org/c-sharp-char-equals-method/)

在 C# 中， ***Char。*** 是一个*系统。Char* struct 方法，用于通过检查当前实例是否等于指定对象或 Char 值来返回值。这个方法可以通过传递不同类型的参数来重载。

1.  **Char。相等(充电)法**
2.  **Char。相等(对象)方法**

#### 夏尔。相等(字符)方法

此方法用于通过检查当前实例是否等于指定的 Char 对象来返回值。

**语法:**

```cs
public bool Equals(Char ob);
```

**参数:**

> **ob** :需要与当前实例的值进行比较的对象。

**返回类型:**如果给定的 *ob* 参数等于当前实例的值，则返回*真*否则返回*假*。该方法的返回类型为*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.Equals(Char) Method
using System;

public class GeeksforGeeks {

    // Main method
    public static void Main() {

        // declaration of datatype
        bool result;
        char ch1 = 'G';

        // checking if 'G' is equal or not

        // Here we are passing char G as the
        // parameter to the Equals Method
        result = ch1.Equals('G');

        Console.WriteLine(result);    

        // checking if 'v' is equal or not
        char ch2 = 'v';

        // Here we are passing char W as the
        // parameter to the Equals Method
        result = ch2.Equals('W');

        Console.WriteLine(result);        
    }
}
```

**Output:**

```cs
True
False

```

#### 夏尔。等于(对象)方法

此方法用于通过检查当前实例是否等于指定的对象来返回值。

**语法:**

```cs
public override bool Equals(object ob);
```

**参数:**

> **ob** :需要与当前实例进行比较的对象，或者 *null* 。

**返回类型:**如果给定的 *ob* 参数是 Char 的一个实例，并且等于当前实例的值，则返回*真*否则返回*假*。该方法的返回类型为*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.Equals(Object) Method
using System;

public class GeeksforGeeks {

    // Main method
    public static void Main() {

        // Declaration of data type
        bool result;

        // Checking if 'G' is equal or not
        char ch1 = 'G';

        // Here we are passing object ch1 as the
        // parameter to the Equals Method
        result = 'G'.Equals(ch1);

        Console.WriteLine(result);  

        // Checking if 'v' is equal or not
        char ch2 = 'v';

         // Here we are passing object ch2 as the
        // parameter to the Equals Method
        result = 'x'.Equals(ch2);

        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False

```

**参考:**T2？视图=netframework-4.7.2