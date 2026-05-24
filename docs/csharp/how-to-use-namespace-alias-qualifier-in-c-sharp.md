# 如何在 C# 中使用::命名空间别名限定符

> 原文:[https://www . geesforgeks . org/how-用法-名称空间-别名-限定符-in-c-sharp/](https://www.geeksforgeeks.org/how-to-use-namespace-alias-qualifier-in-c-sharp/)

**名称空间别名限定符( *::* )** 使用别名来代替更长的名称空间，并且它提供了一种避免类的模糊定义的方法。它总是位于两个标识符之间。限定符看起来像两个冒号(::)，带有别名和类名。它可以是全球性的。因此，它不会调用别名命名空间中的查找，而是调用全局命名空间中的查找。

**语法:**

```cs
alias_name::class-name;
```

**示例:**

```cs
// C# program to illustrate how to use
// the :: Namespace Alias Qualifier
using System;

// creating aliased name
using first = firstnamespace;
using sec = secondnamespace;

namespace Geeks {

class GFG {

    // Main Method
    static void Main()
    {

        // use of Namespace alias qualifier(::)
        first::GFG1 obj1 = new first::GFG1(); 
        obj1.display();
    }
}
}

// Both namespaces have a 
// class named GFG1
namespace firstnamespace {

class GFG1 {

    public void display()
    {
        Console.WriteLine("It is the first namespace.");
    }
}
}

namespace secondnamespace {

class GFG1 {

    public void display()
    {
        Console.WriteLine("It is the second namespace.");
    }
}
}
```

**Output:**

```cs
It is the first namespace.

```

**注意:**名称空间别名限定符**:**仅用于名称空间或别名，不能用于子类。

**示例:**

```cs
System.Collections::lists obj= new System.Collections.lists() // illegal
aliasname = System.Collections;
aliasname::lists obj = new aliasname::lists(); // Legal

```

```cs
// C# program to illustrate how to use
// the :: Namespace Alias Qualifier
using aliasname = System.Collections;

namespace Geeks {

class GFG {

    // Main Method
    static void Main()
    {
        // using :: Namespace Alias Qualifier
        aliasname::Hashtable obj = new aliasname::Hashtable();

        // Add items to the table.
        obj.Add("ASCII value of A is:", "65");
        obj.Add("ASCII value of B is:", "66");

        // displaying the result
        foreach(string i in obj.Keys)
        {
            System.Console.WriteLine(i + " " + obj[i]);
        }
    }
}
}
```

**Output:**

```cs
ASCII value of A is: 65
ASCII value of B is: 66

```