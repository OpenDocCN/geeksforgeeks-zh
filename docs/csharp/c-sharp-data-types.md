# C# |数据类型

> 原文:[https://www.geeksforgeeks.org/c-sharp-data-types/](https://www.geeksforgeeks.org/c-sharp-data-types/)

数据类型指定有效的 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 变量可以保存的数据类型。C# 是一种**强类型编程语言**，因为在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，每种类型的数据(如整数、字符、浮点等)都是作为编程语言的一部分预定义的，为给定程序定义的所有常量或变量都必须用其中一种数据类型来描述。

### 

**数据类型在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中主要分为三类**

*   **数值数据类型**
*   **参考数据类型**
*   **指针数据类型**

1.  **值数据类型:**在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，值数据类型将直接将变量值存储在内存中，它还将接受有符号和无符号文本。这些数据类型的派生类是**系统。值类型**。以下是 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 编程语言中**不同的值数据类型**:
    *   **有符号&无符号整数类型:**有 8 种整数类型，支持 8 位、16 位、32 位和 64 位有符号或无符号形式的值。T67】系统 Int64 T93】零 T95】乌肖特 T99】无符号整数 T3【乌龙】T4

        | 别名 | 类型名 | 类型 | 大小（位) | 范围 | 缺省值 |
        | --- | --- | --- | --- | --- | --- |
        | sbyte(字节) | 系统 Sbyte | 带符号整数 | 八 | -128 到 127 | 零 |
        | 短的 | 系统 Int16 | 带符号整数 | 十六 | -32768 到 32767 | 零 |
        | 同国际组织)国际组织 | 系统 Int32 | 带符号整数 | 三十二 | -二<sup>三十一</sup>至 2 <sup>31</sup> -1 | 零 | 长的 | 带符号整数 | 六十四 | -二 <sup>63</sup> 至 2<sup>63</sup>-1 | 0L |
        | 字节 | System.byte | 无符号整数 | 八 | 0 到 255 | 系统 uint 16 | 十六 | 0 到 65535 | 零 |
        | uint | 系统 UInt32 | 无符号整数 | 三十二 | 0 至 2 <sup>32</sup> | 0 | 系统 UInt64 | 无符号整数 | 64 | 0 至 2<sup>63</sup> | 0 |

    *   **浮点类型:**包含小数点的浮点数据类型有 2 种。

        *   **浮点**:是 **32 位单精度**浮点类型。它有 7 位数的精度。要初始化一个浮点变量，使用后缀 f 或 F. Like，float x = 3.5F。如果后缀 F 或 F 不使用，那么它被视为双。
        *   **双**:是 **64 位双精度**浮点型。它有 14-15 位精度。若要初始化双精度变量，请使用后缀 d 或 d。但不一定要使用后缀，因为默认情况下，浮动数据类型是双精度类型。

        | 别名 | 类型名 | 大小(位) | 范围(约) | 缺省值 |
        | --- | --- | --- | --- | --- |
        | 漂浮物 | 系统。单一的 | Thirty-two | 1.5 × 10 <sup>-45</sup> 至 3.4 × 10 <sup>38</sup> | 0.0F |
        | 两倍 | 系统。两倍 | Sixty-four | 5.0 × 10 <sup>-324</sup> 至 1.7 × 10 <sup>308</sup> | 0.0D |

    *   **十进制类型:**十进制类型是适用于金融和货币计算的 128 位数据类型。它有 28-29 位精度。若要初始化十进制变量，请使用后缀 m 或 m。Like as，十进制 x = 300.5m。如果后缀 M 或 M 不使用，那么它被视为双。T21】系统。小数

        | 别名 | 类型名 | 大小（位) | 范围（约) | 缺省值 |
        | --- | --- | --- | --- | --- |
        | 小数 | 一百二十八 | 1.0 × 10 <sup>-28</sup> 至 7.9228×10<sup>28</sup> | 0.0M |

    *   **Character Types :** The character types represents a UTF-16 code unit or represents the 16-bit Unicode character.

        | 别名 | 类型名 | 尺寸单位(位) | 范围 | 缺省值 |
        | --- | --- | --- | --- | --- |
        | 茶 | 系统。茶 | Sixteen | U +0000 至 U +ffff | ‘\0’ |

        **示例:**

        ```cs
        // C# program to demonstrate 
        // the above data types
        using System;
        namespace ValueTypeTest {

        class GeeksforGeeks {

            // Main function
            static void Main()
            {

                // declaring character
                char a = 'G';

                // Integer data type is generally
                // used for numeric values
                int i = 89;

                short s = 56;

                // this will give error as number
                // is larger than short range
                // short s1 = 87878787878;

                // long uses Integer values which 
                // may signed or unsigned
                long l = 4564;

                // UInt data type is generally
                // used for unsigned integer values
                uint ui = 95;

                ushort us = 76;
                // this will give error as number is
                // larger than short range

                // ulong data type is generally
                // used for unsigned integer values
                ulong ul = 3624573;

                // by default fraction value
                // is double in C#
                double d = 8.358674532;

                // for float use 'f' as suffix
                float f = 3.7330645f;

                // for float use 'm' as suffix
                decimal dec = 389.5m;

                Console.WriteLine("char: " + a);
                Console.WriteLine("integer: " + i);
                Console.WriteLine("short: " + s);
                Console.WriteLine("long: " + l);
                Console.WriteLine("float: " + f);
                Console.WriteLine("double: " + d);
                Console.WriteLine("decimal: " + dec);
                Console.WriteLine("Unsinged integer: " + ui);
                Console.WriteLine("Unsinged short: " + us);
                Console.WriteLine("Unsinged long: " + ul);
            }
        }
        }
        ```

        **输出:**

        ```cs
        char: G
        integer: 89
        short: 56
        long: 4564
        float: 3.733064
        double: 8.358674532
        decimal: 389.5
        Unsinged integer: 95
        Unsinged short: 76
        Unsinged long: 3624573

        ```

        **示例:**

        ```cs
        // C# program to demonstrate the Sbyte
        // signed integral data type
        using System;
        namespace ValueTypeTest {

        class GeeksforGeeks {

            // Main function
            static void Main()
            {
                sbyte a = 126;

                // sbyte is 8 bit 
                // singned value
                Console.WriteLine(a);

                a++;
                Console.WriteLine(a);

                // It overflows here because
                // byte can hold values 
                // from -128 to 127
                a++;
                Console.WriteLine(a);

                // Looping back within 
                // the range
                a++;
                Console.WriteLine(a);
            }
        }
        }
        ```

        **输出:**

        ```cs
        126
        127
        -128
        -127

        ```

        **示例:**

        ```cs
        // C# program to demonstrate 
        // the byte data type
        using System;
        namespace ValueTypeTest {

        class GeeksforGeeks {

            // Main function
            static void Main()
            {
                byte a = 0;

                // byte is 8 bit 
                // unsigned value
                Console.WriteLine(a);

                a++;
                Console.WriteLine(a);

                a = 254;

                // It overflows here because
                // byte can hold values from
                // 0 to 255
                a++;
                Console.WriteLine(a);

                // Looping back within the range
                a++;
                Console.WriteLine(a);
            }
        }
        }
        ```

        **输出:**

        ```cs
        0
        1
        255
        0

        ```

    *   **Boolean Types :** It has to be assigned either true or false value. Values of type bool are not converted implicitly or explicitly (with casts) to any other type. But the programmer can easily write conversion code.

        | 别名 | 类型名 | 价值观念 |
        | --- | --- | --- |
        | 弯曲件 | 系统。布尔代数学体系的 | 真/假 |

        **示例:**

        ```cs
        // C# program to demonstrate the
        // boolean data type
        using System;
        namespace ValueTypeTest {

            class GeeksforGeeks {

            // Main function
            static void Main() 
            {

                // boolean data type
                bool b = true;     
                if (b == true)
                    Console.WriteLine("Hi Geek");
            } 
        }
        }
        ```

        **输出:**

        ```cs
        Hi Geek

        ```

2.  **引用数据类型:**引用数据类型将包含变量值的内存地址，因为引用类型不会将变量值直接存储在内存中。内置引用类型有**字符串、对象。**
    *   **字符串:**代表一系列 Unicode 字符，其类型名为**系统。弦**。所以，字符串和 string 是等价的。
        **例:**

        ```cs
        string s1 = "hello"; // creating through string keyword  
        String s2 = "welcome"; // creating through String class  

        ```

    *   **Object :** In C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from Object. So basically it is the base class for all the data types in C#. Before assigning values, it needs type conversion. When a variable of a value type is converted to object, it’s called **boxing**. When a variable of type object is converted to a value type, it’s called **unboxing**. Its type name is **System.Object**.

        **示例:**

        ```cs
        // C# program to demonstrate 
        // the Reference data types
        using System;
        namespace ValueTypeTest {

        class GeeksforGeeks {

            // Main Function
            static void Main() 
            {

                // declaring string
                string a = "Geeks"; 

                //append in a
                a+="for";
                a = a+"Geeks"; 
                Console.WriteLine(a);

                // declare object obj
                object obj;
                obj = 20;
                Console.WriteLine(obj);

                // to show type of object
                // using GetType()
                Console.WriteLine(obj.GetType()); 
            } 
        }
        }
        ```

        **输出:**

        ```cs
        GeeksforGeeks
        20
        System.Int32

        ```

3.  **Pointer Data Type :** The Pointer Data Types will contain a memory address of the variable value.
    To get the pointer details we have a two symbols **ampersand (&) and asterisk (*)**.
    ***ampersand (&)*:** It is Known as Address Operator. It is used to determine the address of a variable.
    ***asterisk (*)*:** It also known as Indirection Operator. It is used to access the value of an address.
    **Syntax :**

    ```cs
    type* identifier;

    ```

    **示例:**

    ```cs
    int* p1, p;   // Valid syntax
    int *p1, *p;   // Invalid 

    ```

    **示例:**

    ```cs
    // Note: This program will not work on
    // online compiler
    // Error: Unsafe code requires the `unsafe' 
    // command line option to be specified
    // For its solution:
    // Go to your project properties page and
    // check under Build the checkbox Allow
    // unsafe code.
    using System;
    namespace Pointerprogram {

    class GFG {

        // Main function
        static void Main()
        {
            unsafe
            {

                // declare variable
                int n = 10;

                // store variable n address 
                // location in pointer variable p
                int* p = &n;
                Console.WriteLine("Value :{0}", n);
                Console.WriteLine("Address :{0}", (int)p);
            }
        }
    }
    }
    ```