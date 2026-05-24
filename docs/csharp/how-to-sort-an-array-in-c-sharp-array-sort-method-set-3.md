# 如何在 C# | Array 中对数组进行排序。排序()方法集–3

> 原文:[https://www . geeksforgeeks . org/如何对 c-sharp-array-sort-method-set-3/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-3/)

**阵列。排序方法**用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法:

*   **排序(数组、比较器)方法***   **排序(数组、数组、比较器)方法***   **Sort(Array, Array) Method

    #### 排序(数组、比较器)方法

    此方法使用指定的 *IComparer* 对一维数组中的元素进行排序。

    > **语法:**公共静态 void Sort (Array arr，IComparer comparer)；
    > 
    > **参数:**
    > **arr:** 是要排序的一维数组。
    > **比较器:**是比较元素时使用的实现。

    **异常:**

    *   **参数空异常:**如果数组 *arr* 为空。
    *   **rankeexception:**如果数组 **arr** 是多维的。
    *   **无效操作异常:**如果**比较器**为空。
    *   **ArgumentException:** 如果**比较器**的实现在排序过程中导致错误。

    **例 1:**

    ```cs
    // C# program to demonstrate the 
    // Array.Sort(Array, IComparer) method
    using System;
    using System.Collections;

    class compare : IComparer {

        // Call CaseInsensitiveComparer.Compare
        public int Compare(Object x, Object y)
        {
            return (new CaseInsensitiveComparer()).Compare(x, y);
        }
    }

    class GFG {

        // Main Method
        public static void Main()
        {

            // Initializing array.
            String[] arr = {"A", "D", "B",
                      "E", "C", "F", "G"};

            // Instantiate the IComparer object
            IComparer cmp = new compare();

            // Display the original values of the array
            Console.WriteLine("The Original array:");
            display(arr);

            // Sort the entire array by using
            // the IComparer object
            // "cmp" is the IComparer object
            Array.Sort(arr, cmp);

            Console.WriteLine("\nAfter sorting the array"+
                                 " using the IComparer:");
            display(arr);
        }

        // display function
        public static void display(String[] arr)
        {
            foreach(String a in arr)
                Console.WriteLine(a);
        }
    }
    ```

    **Output:**

    ```cs
    The Original array:
    A
    D
    B
    E
    C
    F
    G

    After sorting the array using the IComparer:
    A
    B
    C
    D
    E
    F
    G

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the 
    // Array.Sort(Array, IComparer) method
    using System;
    using System.Collections;

    class compare : IComparer {

        // Call CaseInsensitiveComparer.Compare
        public int Compare(Object x, Object y)
        {
            return (new CaseInsensitiveComparer()).Compare(x, y);
        }
    }

    class GFG {

        // Main Method
        public static void Main()
        {
            // Initializing array.
            int[] arr = {10, 1, 9, 8, 3,
                         4, 6, 5, 2, 7};

            // Instantiate the IComparer object
            IComparer cmp = new compare();

            // Display the original values of the array
            Console.WriteLine("The Original array:");
            display(arr);

            // Sort the entire array by 
            // using the IComparer object
            // "cmp" is the IComparer object
            Array.Sort(arr, cmp);

            Console.WriteLine("\n\nAfter sorting the "+
                         "array using the IComparer:");

            display(arr);
        }

        // display function
        public static void display(int[] arr)
        {
            foreach(int a in arr)
                Console.Write(a + " ");
        }
    }
    ```

    **Output:**

    ```cs
    The Original array:
    10 1 9 8 3 4 6 5 2 7 

    After sorting the array using the IComparer:
    1 2 3 4 5 6 7 8 9 10

    ```

    #### 排序(数组、数组、比较器)方法

    该方法使用指定的*比较器*根据第一个数组中的*键*对一对一维数组对象进行排序。

    > **语法:**公共静态 void Sort(数组键、数组项、IComparer 比较器)；
    > 
    > **参数:**
    > **键:**包含要排序的键的一维数组。
    > **项:**是一维数组，包含与*键*数组中每个键对应的项。
    > **比较器:**比较元素时使用的是 *IComparer* 实现。

    **异常:**

    *   **参数空异常:**如果*键*为空。
    *   **rankeexception:**如果*键*数组是多维的或者*项*数组是多维的。
    *   **参数异常:**如果*项*不为空，*键*的长度大于*项*的长度，或者*比较器*的实现导致排序出错。
    *   **无效操作异常:**如果*比较器*为空。

    **示例:**

    ```cs
    // C# program to demonstrate the 
    // Array.Sort(Array, Array, 
    // IComparer) method
    using System;
    using System.Collections;

    class comparer : IComparer {

        // Call CaseInsensitiveComparer.Compare
        public int Compare(Object x, Object y)
        {
            return (new CaseInsensitiveComparer()).Compare(x, y);
        }
    }

    class GFG {

        // Main Method
        public static void Main()
        {
            // initialize two arrays
            String[] arr1 = {"H", "J", "K",
                       "L", "I", "N", "M"};

            String[] arr2 = {"A", "E", "D",
                       "C", "F", "B", "G"};

            // Instantiate the IComparer object
            IComparer g = new comparer();

            // Display original values of the array.
            Console.WriteLine("The original order of "+
                             "elements in the array:");

            Display(arr1, arr2);

            // Sort the array using IComparer 
            // object. "g" is IComparer object
            Array.Sort(arr1, arr2, g);

            Console.WriteLine("\nAfter sorting :");
            Display(arr1, arr2);
        }

        // Display function
        public static void Display(String[] arr1, String[] arr2)
        {
            for (int i = 0; i < arr1.Length; i++) {
                Console.WriteLine(arr1[i] + " : " + arr2[i]);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The original order of elements in the array:
    H : A
    J : E
    K : D
    L : C
    I : F
    N : B
    M : G

    After sorting :
    H : A
    I : F
    J : E
    K : D
    L : C
    M : G
    N : B

    ```

    #### 排序(数组，数组)方法

    该方法基于第一个数组中的*键*对一对一维数组对象进行排序，使用每个键的 *IComparable* 实现。这里，在对象中有两个数组，其中一个包含键，另一个包含相应的项。

    > **语法:**公共静态空排序(数组键，数组项)；
    > 
    > **参数:**
    > **键:**包含要排序的键的一维数组。
    > **项:**是一维数组，包含与*键*数组中每个键对应的项。

    **异常:**

    *   **参数空异常:**如果*键*为空。
    *   **rankeexception:**如果*键*数组是多维的或者*项*数组是多维的。
    *   **参数异常:**如果*项*不为空且*键*的长度大于*项*的长度。
    *   **无效操作异常:**如果*键*数组中的一个或多个元素没有实现*可比较*界面。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // Array.Sort(Array, Array) method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // initialize two array.
            int[] arr1 = {7, 5, 2, 3, 1, 6, 4};
            string[] arr2 = {"A", "E", "D",
                       "C", "F", "B", "G"};

            // Display original values of the array.
            Console.WriteLine("The original array:");
            Display(arr1, arr2);

            // Sort the array using two array
            // "arr1" is keys array
            // "arr2" item array
            Array.Sort(arr1, arr2);

            Console.WriteLine("\nAfter Sorting :");
            Display(arr1, arr2);
        }

        // Display function
        public static void Display(int[] arr1, string[] arr2)
        {
            for (int i = 0; i < arr1.Length; i++) 
            {
                Console.WriteLine(arr1[i] + " : " + arr2[i]);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The original array:
    7 : A
    5 : E
    2 : D
    3 : C
    1 : F
    6 : B
    4 : G

    After Sorting :
    1 : F
    2 : D
    3 : C
    4 : G
    5 : E
    6 : B
    7 : A

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . sort？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2)**