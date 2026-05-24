# 如何使用数组。C# 中的 BinarySearch()方法| Set -2

> 原文:[https://www . geesforgeks . org/如何使用-数组-binary search-method-in-c-sharp-set-2/](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-2/)

*阵列。BinarySearch()方法*用于在排序的[一维数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中搜索一个值。该方法使用了[二分搜索法算法](https://www.geeksforgeeks.org/binary-search/)。该算法通过重复地将搜索间隔分成两半来搜索排序的数组。从覆盖整个数组的间隔开始。如果搜索关键字的值小于间隔中间的项目，请将间隔缩小到下半部分。否则，缩小到上半部分。反复检查，直到找到值或间隔为空。

*该方法重载列表中共有 8 种方法，如下:*

*   **[二进制搜索(数组、对象)方法](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 1st)***   **[二进制搜索(数组、对象、比较器)方法](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 2nd)***   **[BinarySearch(数组，Int32，Int32，Object)方法](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 3rd)***   **[二进制搜索(数组，Int32，Int32，对象，IComparer)方法](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 4th)***   **BinarySearch <t>(T[]，T)方法</t>***   **BinarySearch <t>(T[]，T，IComparer <t>)方法</t></t>***   **BinarySearch <t>(T[]，Int32，Int32，T)方法</t>***   **BinarySearch<T>(T[], Int32, Int32, T, IComparer<T>) Method

    这里前 4 种方法已经在 **[集合-1](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/)** 中讨论过了。最后 4 种方法将在本集中讨论

    #### BinarySearch <t>(T[]，T)方法</t>

    此方法在排序的一维数组中搜索特定元素。它将搜索整个数组。搜索使用由数组的每个元素或特定对象实现的 **IComparable < T >** 通用接口。

    > **语法:**公共静态 int binary search<T>(T[]arr，T val)；
    > 在这里，**“T”**是阵的元素类型。
    > 
    > **参数:**
    > **arr:** 是要搜索的一维排序数组。
    > **val:** 是要搜索的对象。

    **返回值:**如果找到*值*，则返回指定 *arr* 中指定*值*的索引，否则返回负数。返回值有如下几种不同的情况:

    *   如果未找到 *val* ，并且 *val* 小于 *arr* 中的一个或多个元素，则返回的负数是大于 *val* 的第一个元素的索引的按位补码。
    *   如果未找到*值*，并且*值*大于 *arr* 中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
    *   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使 *arr* 中存在*值*。

    **异常:**

    *   **参数空异常:**如果 *arr* 为空。
    *   **无效操作异常:**如果 *T* 没有实现 IComparable < T >通用接口。

    **例 1:**

    ```cs
    // C# program to demonstrate the use of 
    // BinarySearch<T>(T[], T) method
    using System;
    using System.Collections.Generic;

    class GFG {

        // Main Method
        public static void Main()
        {
            string[] arr = {"ABC", "XYZ",
                    "JKL", "DEF", "MNO"};

            Console.WriteLine("Original array");
            foreach(string g in arr)
            {
                Console.WriteLine(g);
            }

            Console.WriteLine("\nAfter Sort");

            // sort the array
            Array.Sort(arr);

            foreach(string g in arr)
            {
                Console.WriteLine(g);
            }

            Console.WriteLine("\nBinarySearch for 'GHI':");

             // call "BinarySearch<T>(T[], T)" method
            int index = Array.BinarySearch(arr, "GHI");

            sortt(arr, index);

        }

        // BinarySearch<T> method
        private static void sortt<T>(T[] array, int index)
        {
            if (index < 0) 
            {

                // If the index is negative, 
                // it represents the bitwise
                // complement of the next 
                // larger element in the array.
                index = ~index;

                Console.Write("Sorts between: ");

                if (index == 0)
                    Console.Write("beginning of array and ");
                else
                    Console.Write("{0} and ", array[index - 1]);

                if (index == array.Length)
                    Console.WriteLine("end of array.");
                else
                    Console.WriteLine("{0}.", array[index]);
            }
            else 
            {
                Console.WriteLine("Found at index {0}.", index);
            }
        }
    }
    ```

    **Output:**

    ```cs
    Original array
    ABC
    XYZ
    JKL
    DEF
    MNO

    After Sort
    ABC
    DEF
    JKL
    MNO
    XYZ

    BinarySearch for 'GHI':
    Sorts between: DEF and JKL.

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the use 
    // of BinarySearch<T>(T[], T) method
    using System;
    using System.Collections.Generic;

    class GFG {

        // Main Method
        public static void Main()
        {
            int[] arr = {5, 7, 1, 3, 4, 2};

            Console.WriteLine("Original array");

            foreach(int g in arr)
            {
                Console.WriteLine(g);
            }

            Console.WriteLine("\nAfter Sort");

            // sort the array
            Array.Sort(arr);

            foreach(int g in arr)
            {
                Console.WriteLine(g);
            }

            Console.WriteLine("\nBinarySearch for '6':");

            // call "BinarySearch<T>(T[], T)" method
            int index = Array.BinarySearch(arr, 6);

            sortt(arr, index);

        }

        // BinarySearch<T> method
        private static void sortt<T>(T[] array, int index)
        {
            if (index < 0) 
            {

                // If the index is negative,
                // it represents the bitwise
                // complement of the next 
                // larger element in the array.
                index = ~index;

                Console.Write("Sorts between: ");

                if (index == 0)
                    Console.Write("beginning of array and ");
                else
                    Console.Write("{0} and ", array[index - 1]);

                if (index == array.Length)
                    Console.WriteLine("end of array.");
                else
                    Console.WriteLine("{0}.", array[index]);
            }
            else 
            {
                Console.WriteLine("Found at index {0}.", index);
            }
        }
    }
    ```

    **Output:**

    ```cs
    Original array
    5
    7
    1
    3
    4
    2

    After Sort
    1
    2
    3
    4
    5
    7

    BinarySearch for '6':
    Sorts between: 5 and 7.

    ```**