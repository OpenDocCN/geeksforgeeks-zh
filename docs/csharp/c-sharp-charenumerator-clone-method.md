# C# | CharEnumerator。克隆()方法

> 原文:[https://www . geesforgeks . org/c-sharp-charenumerator-clone-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-clone-method/)

**CharEnumerator。克隆方法**用于创建当前**查点器**对象的副本。这对于在遍历字符串对象时保存当前状态非常有用。

**语法:**

```cs
public object Clone ();
```

**返回值:**该方法返回一个对象，该对象是当前*查点器*对象和当前*查点器*对象的副本。

下面是说明使用**字符枚举器的程序。克隆()**方法:

**例 1:**

```cs
// C# program to illustrate the
// CharEnumerator.Clone Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "The Sun rises in the East,sets in the West.";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        while (chEnum.MoveNext()) 
        {
            // Printing the characters
            Console.Write(chEnum.Current);

            // Break when a space is encountered
            if (chEnum.Current == ',') 
            {
                Console.WriteLine();
                break;
            }
        }

        // Instantiate a copy of CharEnumerator
        // object with the current state
        CharEnumerator chEnumCopy = (CharEnumerator)chEnum.Clone();

        // Printing the rest of the characters
        while (chEnumCopy.MoveNext())
            Console.Write(chEnumCopy.Current);
    }
}
```

**Output:**

```cs
The Sun rises in the East,
sets in the West.

```

**例 2:**

```cs
// C# program to illustrate the
// CharEnumerator.Clone Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "1234567";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        while (chEnum.MoveNext())
        {
            // Print current character
            Console.Write(chEnum.Current + " ");

            // Instantiate a copy of CharEnumerator 
            // object with current state
            CharEnumerator chEnumCopy = (CharEnumerator)chEnum.Clone();

            // Printing all characters 
            // after the current position
            while (chEnumCopy.MoveNext())
                Console.Write(chEnumCopy.Current + " ");

            Console.WriteLine();
        }
    }
}
```

**Output:**

```cs
1 2 3 4 5 6 7 
2 3 4 5 6 7 
3 4 5 6 7 
4 5 6 7 
5 6 7 
6 7 
7

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . charenumerator . clone？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.charenumerator.clone?view=netframework-4.7.2)