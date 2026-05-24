# C# |反转整个数组列表或指定范围内元素的顺序

> 原文:[https://www . geeksforgeeks . org/c-sharp-反转整个数组列表或指定范围内元素的顺序/](https://www.geeksforgeeks.org/c-sharp-reverse-the-order-of-the-elements-in-the-entire-arraylist-or-in-the-specified-range/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。反转方法**用于反转数组列表中元素在指定范围内的顺序。*数组列表的重载列表中有两种方法。反向*方法如下:

*   **数组列表。反向()***   **ArrayList.Reverse(Int32, Int32)

    #### 数组列表。反向()方法

    此方法用于反转整个数组列表中元素的顺序。

    **语法:**

    ```cs
    public virtual void Reverse ();

    ```

    **异常:**如果数组列表是只读的，这个方法将给出 *NotSupportedException* 。

    **注:**此方法为 O(n)运算，其中 n 为 Count。

    下面给出了一些例子，以便更好地理解实现:

    **例 1:**

    ```cs
    // C# code to reverse the order of
    // the elements in the entire ArrayList
    using System;
    using System.Collections;

    class GFG {

        // Driver code
        public static void Main()
        {

            // Creating an ArrayList
            ArrayList myList = new ArrayList(5);

            // Adding elements to ArrayList
            myList.Add("First");
            myList.Add("Second");
            myList.Add("Third");
            myList.Add("Fourth");
            myList.Add("Fifth");

            // Reversing the order of elements in entire ArrayList
            myList.Reverse();

            // Displaying the elements in myList
            for (int i = 0; i < myList.Count; i++) {
                Console.WriteLine(myList[i]);
            }
        }
    }
    ```

    **输出:**

    ```cs
    Fifth
    Fourth
    Third
    Second
    First

    ```

    **例 2:**

    ```cs
    // C# code to reverse the order of
    // the elements in the entire ArrayList
    using System;
    using System.Collections;

    class GFG {

        // Driver code
        public static void Main()
        {

            // Creating an ArrayList
            ArrayList myList = new ArrayList(5);

            // Adding elements to ArrayList
            myList.Add(1);
            myList.Add(2);
            myList.Add(3);
            myList.Add(4);
            myList.Add(5);

            // Reversing the order of elements in entire ArrayList
            myList.Reverse();

            // Displaying the elements in myList
            for (int i = 0; i < myList.Count; i++) {
                Console.WriteLine(myList[i]);
            }
        }
    }
    ```

    **输出:**

    ```cs
    5
    4
    3
    2
    1

    ```

    #### 数组列表。反向(Int32，Int32)

    此方法用于反转指定范围内元素的顺序。

    **语法:**

    ```cs
    public virtual void Reverse (int index, int count);

    ```

    **参数:**

    > **指数:**是要反转的区间的从零开始的指数。
    > 
    > **计数:**是要反转的范围内的元素数量。

    **异常:**

    *   **argumentoutofrangerexception:**如果索引小于零或者计数小于零。
    *   **参数异常:**如果索引和计数不表示数组列表中元素的有效范围。
    *   **notSupportDexception:**如果数组列表是只读的或者数组列表具有固定的大小。

    **注:**此方法为 O(n)运算，其中 n 为 Count。

    下面给出了一些例子，以便更好地理解实现:

    **例 1:**

    ```cs
    // C# code to reverse a sub 
    // range in the ArrayList
    using System; 
    using System.Collections;

    class GFG {

    // Driver code
    public static void Main() { 

        // Creating an ArrayList
        ArrayList myList = new ArrayList(5);

        // Adding elements to ArrayList
        myList.Add("First");
        myList.Add("Second");
        myList.Add("Third");
        myList.Add("Fourth");
        myList.Add("Fifth");

        // Reversing the sub-range
        // starting from index 1, and 
        // count 3 elements
        myList.Reverse(1, 3);

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
          Console.WriteLine(myList[i]);
        }
      } 
    }
    ```

    **输出:**

    ```cs
    First
    Fourth
    Third
    Second
    Fifth

    ```

    **例 2:**

    ```cs
    // C# code to reverse a sub 
    // range in the ArrayList
    using System; 
    using System.Collections;

    class GFG {

    // Driver code
    public static void Main() { 

        // Creating an ArrayList
        ArrayList myList = new ArrayList(5);

        // Adding elements to ArrayList
        myList.Add(4);
        myList.Add(8);
        myList.Add(12);
        myList.Add(16);
        myList.Add(20);

        // Reversing the sub-range
        // starting from index 0, and 
        // count 2 elements
        myList.Reverse(0, 2);

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
          Console.WriteLine(myList[i]);
        }
      } 
    }
    ```

    **输出:**

    ```cs
    8
    4
    12
    16
    20

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . reverse？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.reverse?view=netframework-4.7.2)**