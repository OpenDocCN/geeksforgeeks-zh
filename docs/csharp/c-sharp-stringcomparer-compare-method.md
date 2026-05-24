# C# | StringComparer。比较方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-string comparer-compare-method/](https://www.geeksforgeeks.org/c-sharp-stringcomparer-compare-method/)

**StringComparer。比较方法**用于比较两个对象或字符串，并返回它们相对排序顺序的指示。该方法的重载列表中有 2 种方法:

*   **比较(对象，对象)***   **Compare(String, String)

    #### 比较(对象，对象)

    此方法比较两个对象，并在派生类中重写时返回它们的相对排序顺序的指示。

    **语法:**

    ```cs
    public int Compare (object a, object b);
    ```

    在这里， *a* 是第一个对象， *b* 是第二个要相互比较的对象。

    **返回:**该方法返回一个有符号整数，表示对象 *a* 和 *b* 的相对值。这些值根据下表返回:

    | **值** | **表示** |
    | 小于零 | a 在排序顺序中位于 b 之前，或者 a 为空，b 不为空。 |
    | 零 | a 等于 b 或者 a 和 b 都为空。 |
    | 大于零 | a 在排序顺序中跟在 b 后面，或者 b 为空，a 不为空。 |

    **异常:**如果 a 和 b 都不是 String 对象，a 和 b 都没有实现 IComparable 接口，这个方法会给出 ArgumentException。

    **示例:**

    ```cs
    // C# program to demonstrate the use of
    // StringComparer.Compare(Object, Object)
    // Method
    using System;
    using System.Collections;

    class gfg {

        public class cmp : IComparer {

            // CaseInsensitiveComparer
            int IComparer.Compare(Object x, Object y)
            {
                return ((new CaseInsensitiveComparer()).Compare(x, y));
            }
        }

        // Main Method
        public static void Main()
        {
            // Initialize a string array.
            string[] arr = {"A", "E", "D", "C", "B"};

            // Display original array
            Console.WriteLine("Original array:");
            print(arr);

            // Sort the array using the default comparer.
            Array.Sort(arr);
            Console.WriteLine("Sort using sort function:");
            print(arr);

            // Sort the array using the comparer.
            Array.Sort(arr, new cmp());
            Console.WriteLine("Sorting using compare method :");
            print(arr);
        }

        // print function
        public static void print(IEnumerable list)
        {
            foreach(var v in list)
                Console.WriteLine(v);

            Console.WriteLine();
        }
    }
    ```

    **Output:**

    ```cs
    Original array:
    A
    E
    D
    C
    B

    Sort using sort function:
    A
    B
    C
    D
    E

    Sorting using compare method :
    A
    B
    C
    D
    E

    ```

    #### 比较(字符串，字符串)

    此方法比较两个字符串，并在派生类中重写时返回它们相对排序顺序的指示。

    **语法:**

    ```cs
    public abstract int Compare (string a, string b);
    ```

    这里 *a* 为第一串， *b* 为第二串进行对比。

    **返回:**该方法返回一个有符号整数，表示对象 *a* 和 *b* 的相对值。这些值根据下表返回:

    | **值** | **表示** |
    | 小于零 | a 在排序顺序中位于 b 之前，或者 a 为空，b 不为空。 |
    | 零 | a 等于 b 或者 a 和 b 都为空。 |
    | 大于零 | a 在排序顺序中跟在 b 后面，或者 b 为空，a 不为空。 |

    **异常:**如果 a 和 b 都不是 String 对象，a 和 b 都没有实现 IComparable 接口，这个方法会给出 ArgumentException。

    **示例:**

    ```cs
    // C# program to demonstrate the use of 
    // StringComparer.Compare(String, String)
    // Method
    using System;
    using System.Collections.Generic;

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            string s1 = "geek";
            string s2 = "Geek";

            int st = 0;

            // Compare(string, string) method
            st = string.Compare(s1, s2);

            Console.WriteLine(st.ToString());
        }
    }
    ```

    **Output:**

    ```cs
    -1

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . string comparer . compare？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.stringcomparer.compare?view=netframework-4.8)**