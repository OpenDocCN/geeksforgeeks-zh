# C# |获取一个遍历 stringDictionary 的枚举数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-in-through-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-stringdictionary/)

**StringDictionary。GetEnumerator** 方法用于返回遍历字符串字典的枚举数。

**语法:**

```cs
public virtual System.Collections.IEnumerator GetEnumerator ();

```

**返回值:**一个迭代字符串字典的[迭代器](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator?view=netframework-4.7.2)。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get an enumerator
// that iterates through the stringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // "IEnumerator" interface supports a simple
        // iteration over a non-generic collection.
        IEnumerator myEnumerator = myDict.GetEnumerator();

        DictionaryEntry de;

        // "MoveNext" advances the enumerator
        // to the next element of the collection.
        // you must call "MoveNext" to advance the
        // enumerator to the first element of the
        // collection before reading the value of "Current"
        while (myEnumerator.MoveNext()) {

            // "Current" returns the same object until
            // either "MoveNext" is called.
            // "MoveNext" sets "Current" to the next element.
            de = (DictionaryEntry)myEnumerator.Current;
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
d Dog
b Banana
c Cat
a Apple

```

**例 2:**

```cs
// C# code to get an enumerator
// that iterates through the stringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("I", "one");
        myDict.Add("II", "two");
        myDict.Add("III", "three");
        myDict.Add("IV", "four");
        myDict.Add("V", "five");

        // "IEnumerator" interface supports a simple
        // iteration over a non-generic collection.
        IEnumerator myEnumerator = myDict.GetEnumerator();

        DictionaryEntry de;

        // "MoveNext" advances the enumerator
        // to the next element of the collection.
        // you must call "MoveNext" to advance the
        // enumerator to the first element of the
        // collection before reading the value of "Current"
        while (myEnumerator.MoveNext()) {

            // "Current" returns the same object until
            // either "MoveNext" is called.
            // "MoveNext" sets "Current" to the next element.
            de = (DictionaryEntry)myEnumerator.Current;
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
iv four
i one
iii three
v five
ii two

```

**注:**

*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . get enumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.getenumerator?view=netframework-4.7.2)