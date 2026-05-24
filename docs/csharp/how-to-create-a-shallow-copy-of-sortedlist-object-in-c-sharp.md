# 如何在 C# 中创建 SortedList 对象的浅拷贝

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中的 sortedlist 对象的浅拷贝/](https://www.geeksforgeeks.org/how-to-create-a-shallow-copy-of-sortedlist-object-in-c-sharp/)

***排序列表。克隆()方法*** 用于创建一个[排序列表](https://www.geeksforgeeks.org/c-sortedlist-class/)对象的浅拷贝。

**语法:**

```cs
public virtual object Clone();
```

**返回值:**它返回一个浅拷贝的[排序列表](https://www.geeksforgeeks.org/c-sortedlist-class/)对象。返回值的类型为*对象*。

**注意:**集合的浅拷贝只拷贝集合的元素，无论它们是引用类型还是值类型，但不拷贝引用所引用的对象。新集合中的引用指向与原始集合中的引用指向的对象相同的对象。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to copy the 
// contents of one SortedList 
// to another SortedList. 
using System; 
using System.Collections; 

class Geeks { 

    // Main Method 
    public static void Main(String[] args) 
    { 
            // Creating a SortedList 
            SortedList mySL = new SortedList();

            // Adding elements to SortedList 
            mySL.Add(1, "C");
            mySL.Add(2, "C++");
            mySL.Add(3, "Java");
            mySL.Add(4, "C#");

            // Creating a shallow copy of mySL
            // we need to cast it explicitly
            SortedList myNewSL = (SortedList)mySL.Clone();

            // displaying the elements of mySL
            Console.WriteLine("Elements of mySL: ");

            for (int i = 0; i < mySL.Count; i++)
            { 
                Console.WriteLine("{0}:\t{1}", mySL.GetKey(i), 
                                          mySL.GetByIndex(i)); 
            }

            // displaying the elements of myNewSL
            Console.WriteLine("\nElements of myNewSL: ");

            for (int i = 0; i < myNewSL.Count; i++) 
            { 
                Console.WriteLine("{0}:\t{1}", myNewSL.GetKey(i), 
                                          myNewSL.GetByIndex(i)); 

            } 

    } 
} 
```

**Output:**

```cs
Elements of mySL: 
1:    C
2:    C++
3:    Java
4:    C#

Elements of myNewSL: 
1:    C
2:    C++
3:    Java
4:    C#

```

**例 2:**

```cs
// C# code to copy the 
// contents of one SortedList 
// to another SortedList. 
using System; 
using System.Collections; 

class Geeks { 

    // Main Method 
    public static void Main(String[] args) 
    { 
            // Creating a SortedList 
            SortedList mySL = new SortedList();

            // Adding elements to SortedList 
            mySL.Add(1, "HTML");
            mySL.Add(2, "CSS");
            mySL.Add(3, "PHP");
            mySL.Add(4, "DBMS");

            // Creating a shallow copy of mySL
            // we need to cast it explicitly
            SortedList myNewSL = (SortedList)mySL.Clone();

            // checking for the equality 
            // of References mySL and myNewSL
            Console.WriteLine("Reference Equals: {0}", 
               Object.ReferenceEquals(mySL, myNewSL));

            // displaying the elements of mySL
            Console.WriteLine("Elements of mySL: ");

            for (int i = 0; i < mySL.Count; i++)
            { 
                Console.WriteLine("{0}:\t{1}", mySL.GetKey(i), 
                                          mySL.GetByIndex(i)); 
            }

            // displaying the elements of myNewSL
            Console.WriteLine("\nElements of myNewSL: ");

            for (int i = 0; i < myNewSL.Count; i++) 
            { 
                Console.WriteLine("{0}:\t{1}", myNewSL.GetKey(i), 
                                          myNewSL.GetByIndex(i)); 

            } 

            // Replaces the values at 
            // index 1 of mySL
            mySL.SetByIndex(1, "C#"); 

            Console.WriteLine("\nAfter Replaces Elements in mySL\n");

            // displaying the elements of myNewSL
            Console.WriteLine("\nElements of myNewSL: ");

            for (int i = 0; i < myNewSL.Count; i++) 
            { 
                Console.WriteLine("{0}:\t{1}", myNewSL.GetKey(i), 
                                          myNewSL.GetByIndex(i)); 

            } 

            // displaying the elements of mySL
            Console.WriteLine("\nElements of mySL: ");

            for (int i = 0; i < mySL.Count; i++)
            { 
                Console.WriteLine("{0}:\t{1}", mySL.GetKey(i), 
                                          mySL.GetByIndex(i)); 
            }

    } 
} 
```

**Output:**

```cs
Reference Equals: False
Elements of mySL: 
1:    HTML
2:    CSS
3:    PHP
4:    DBMS

Elements of myNewSL: 
1:    HTML
2:    CSS
3:    PHP
4:    DBMS

After Replaces Elements in mySL

Elements of myNewSL: 
1:    HTML
2:    CSS
3:    PHP
4:    DBMS

Elements of mySL: 
1:    HTML
2:    C#
3:    PHP
4:    DBMS

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . clone？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.clone?view=netframework-4.7.2)