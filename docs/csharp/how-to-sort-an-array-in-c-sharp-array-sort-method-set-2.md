# 如何在 C# | Array 中对数组进行排序。排序()方法集–2

> 原文:[https://www . geeksforgeeks . org/如何对 c-sharp-array-sort-method-set-2/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-2/)

**阵列。排序方法**用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法:

*   **排序(数组，Int32，Int32，IComparer)方法***   **排序(数组，数组，Int32，Int32，IComparer)方法***   **排序(数组，Int32，Int32)方法***   **Sort(Array, Array, Int32, Int32) Method

    #### 排序(数组，Int32，Int32，IComparer)方法

    此方法使用指定的 *IComparer* 对一维数组中某个范围内的元素进行排序。

    > **语法:**公共静态 void Sort (Array arr，int start，int len，IComparer comparer)；
    > 
    > **参数:**
    > 
    > **“arr”:**是要排序的一维数组。
    > **【开始】:**是排序范围的开始指标。
    > **【len】:**是要排序的范围内的元素个数。
    > **“比较器”:**比较元素时使用的是 IComparer 实现，使用每个元素的 *IComparable* 实现则为 null。

    **异常:**

    *   **ArgumentNullException:** 如果数组为空。
    *   **rankeexception:**如果数组是多维的。
    *   **argumentoutofrangerexception**如果*开始*索引小于数组下限或者 *len* 小于零。
    *   **参数异常:**如果*开始*索引和*镜头*没有指定数组中的有效范围，或者如果*比较器*的实现导致排序过程中出错。
    *   **无效操作异常:**如果*比较器*为空，并且数组中的一个或多个元素没有实现 *IComparable* 接口。

    **示例:**

    ```cs
    // C# program to demonstrate the use 
    // of  Array.Sort(Array, Int32, Int32, 
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
            // initialize a array.
            string[] arr = {"ABC", "GHI", "JKL",
                           "DEF", "MNO", "XYZ"};

            // Instantiate the reverse comparer.
            IComparer g = new comparer();

            // Display original values of the array.
            Console.WriteLine("The original order of "+
                              "elements in the array:");
            Display(arr);

            // Sort a section of the array
            // using the IComparer object
            // sorting happens in the range
            // of index 1 to 4
            // "g" is IComparer object
            Array.Sort(arr, 1, 4, g);

            Console.WriteLine("\nAfter sorting in a range of"+
                 " index 1 to 4 using the IComparer object:");

            Display(arr);
        }

        // Display function
        public static void Display(string[] arr)
        {
            for (int i = arr.GetLowerBound(0); 
            i <= arr.GetUpperBound(0); i++) {

                Console.WriteLine(arr[i]);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The original order of elements in the array:
    ABC
    GHI
    JKL
    DEF
    MNO
    XYZ

    After sorting in a range of index 1 to 4 using the IComparer object:
    ABC
    DEF
    GHI
    JKL
    MNO
    XYZ

    ```

    #### 排序(数组，数组，Int32，Int32，IComparer)方法

    此方法使用指定的 IComparer，基于第一个数组中的键对一对一维数组对象中的一系列元素进行排序。这里的对象包含键和相应的项目。

    > **语法:**公共静态 void Sort (Array 键、Array 项、int start、int len、IComparer 比较器)；
    > 
    > **参数:**
    > 
    > **键:**是包含要排序的键的一维数组。
    > **项:**它是一维数组，包含与 keysArray(以前的数组)中的每个键相对应的项。
    > **开始:**是要排序范围的开始指标。
    > **len:** 是要排序的范围内的元素个数。
    > **比较器:**比较元素时使用的是 IComparer 实现，使用每个元素的 *IComparable* 实现则为 null。

    **异常:**

    *   **ArgumentNullException:** 如果密钥为空。
    *   **rankeexception:**如果*键阵*是多维的。
    *   **ArgumentOutOfRangeException:**如果*开始*索引小于键的下限或者*镜头*小于零。
    *   **论证例外:**
        *   如果*项*不为空，并且*键*的下限与*项*的下限不匹配，或者
        *   如果*项*不为空，且*键*的*透镜*大于*项*的长度
        *   如果*开始*索引和 len 没有在键数组中指定有效范围。
        *   如果*项*不为空，并且*开始*索引和*镜头*没有在项数组中指定有效范围。
        *   如果*比较器*的实现导致排序时出错。
    *   **无效操作异常:**如果*比较器*为空。

    **示例:**

    ```cs
    // C# program to demonstrate the use 
    // of Array.Sort(Array, Array, Int32,
    // Int32, IComparer) Method
    using System;
    using System.Collections;

    class comparer : IComparer {

        // Call CaseInsensitiveComparer.Compare
        public int Compare(Object x, Object y)
        {
            return (new CaseInsensitiveComparer()).Compare(y, x);
        }
    }

    // Driver Class
    class GFG {

        // Main Method
        public static void Main()
        {
            // initialize two Arrays
            String[] arr1 = {"H", "J", "K",
                       "L", "I", "N", "M"};

            String[] arr2 = {"A", "E", "D",
                       "C", "F", "B", "G"};

            // Instantiate the reverse comparer.
            IComparer g = new comparer();

            // Display original values of the array.
            Console.WriteLine("The original order of "+
                             "elements in the array:");

            Display(arr1, arr2);

            // Sort a section of the array 
            // using the IComparer object
            // sorting happens in the range
            // of index 1 to 4
            // "g" is IComparer object
            Array.Sort(arr1, arr2, 1, 4, g);

            Console.WriteLine("\nAfter sorting in a "+
                           "range of index 1 to 4 :");

            Display(arr1, arr2);
        }

        // Display function
        public static void Display(String[] arr1, String[] arr2)
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
    The original order of elements in the array:
    H : A
    J : E
    K : D
    L : C
    I : F
    N : B
    M : G

    After sorting in a range of index 1 to 4 :
    H : A
    L : C
    K : D
    J : E
    I : F
    N : B
    M : G

    ```

    #### 排序(数组，Int32，Int32)方法

    此方法使用一维数组中每个元素的 *IComparable* 实现对数组中某个范围内的元素进行排序。

    > **语法:**公共静态 void Sort (Array arr，int start，int len)；
    > 
    > **参数:**
    > 
    > **arr:** 是要排序的一维数组。
    > **开始:**是要排序的区间的开始指标。
    > **len:** 是要排序的范围内的元素个数。

    **异常:**

    *   **ArgumentNullException:** 如果数组为空。
    *   **rankeexception:**如果数组是多维的。
    *   **ArgumentOutOfRangeException:**如果*起始*指数小于数组下限或者 *len* 小于零。
    *   **参数异常:**如果*开始*索引并且*镜头*没有在数组中指定有效范围。
    *   **无效操作异常:**如果数组中的一个或多个元素没有实现 *IComparable* 接口。

    **示例:**

    ```cs
    // C# program to demonstrate the use of
    // Array.Sort(Array, Int32, Int32) method
    using System;
    using System.Collections;

    class GFG {

        // Main Method
        public static void Main()
        {
            // initialize a array.
            string[] arr = {"ABC", "GHI", "JKL",
                           "DEF", "MNO", "XYZ"};

            // Display original values of the array.
            Console.WriteLine("The original order of"+
                           " elements in the array:");

            Display(arr);

            // sorting happens in the
            // range of index 1 to 4
            Array.Sort(arr, 1, 4);

            Console.WriteLine("\nAfter sorting in a range of "+
                   "index 1 to 4 using the IComparer object:");

            Display(arr);
        }

        // Display function
        public static void Display(string[] arr)
        {
            for (int i = arr.GetLowerBound(0); 
            i <= arr.GetUpperBound(0); i++) {

                Console.WriteLine(arr[i]);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The original order of elements in the array:
    ABC
    GHI
    JKL
    DEF
    MNO
    XYZ

    After sorting in a range of index 1 to 4 using the IComparer object:
    ABC
    DEF
    GHI
    JKL
    MNO
    XYZ

    ```**