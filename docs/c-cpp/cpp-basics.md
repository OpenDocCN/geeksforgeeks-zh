# C++ 基础知识

> 原文:[https://www.geeksforgeeks.org/cpp-basics/](https://www.geeksforgeeks.org/cpp-basics/)

C++ 是一种跨平台语言，可用于创建高性能应用程序。它是由比雅尼·斯特劳斯特鲁普开发的，是 C 语言的扩展。该语言在 2011 年、2014 年和 2017 年进行了 3 次重大更新，分别为 C++ 11、C++ 14 和 C++ 17。

### 为什么要用 C++？

*   C++ 是世界上最流行的编程语言之一。
*   C++ 可以在今天的操作系统、图形用户界面和嵌入式系统中找到。
*   C++ 是一种面向对象的编程语言，它为程序提供了清晰的结构，并允许代码被重用，从而降低了开发成本。
*   C++ 是可移植的，可以用来开发适用于多个平台的应用程序。
*   C++ 有趣又易学！
*   由于 C++ 接近 C#和 Java，所以程序员很容易切换到 C++ 或者相反。

### C++ 基础程序

## C++

```cpp
// C++ Hello World Program
#include <iostream>
using namespace std;
int main()
{
  cout << "Hello World!\n";
  return 0;
}
```

**Output**

```cpp
Hello World!
```

### C++ 代码的组件:

1.  [**【评论】**](https://www.geeksforgeeks.org/comments-in-c-c/) **:** 这两个斜杠(//)符号是用来在程序中添加评论的。它对程序的行为或结果没有任何影响。它用来描述你正在编写的程序。
2.  **# include<iostream>:**# include 是用于在我们的程序中包含文件的预处理器指令。这里我们包含了 iostream 标准文件，这是在 C++ 中声明基本标准输入/输出库所必需的。
3.  **使用命名空间标准:**标准 C++ 库的所有元素都在一个命名空间中声明。这里我们使用的是标准命名空间。
4.  **int main():** 任何 C++ 程序的执行都是从 main 函数开始的，因此在你的程序中有一个 main 函数是必要的。“int”是此函数的返回值。(我们稍后将更详细地研究函数)。
5.  **{}:** 花括号用来表示任何函数的起点和终点。每个开口支架都应该有一个相应的封闭支架。
6.  **cout<T3【你好世界！\ n "；**这是 C++ 语句。cout 表示 C++ 中的标准输出流。它在标准命名空间内的 iostream 标准文件中声明。报价之间的文本将打印在屏幕上。\n 不会打印，它用于添加换行符。C++ 中的每个语句都以分号(；).
7.  **返回 0；**返回表示函数结束。这里的函数是 main，所以当我们按 return 0 时，它退出程序。我们返回 0 是因为我们提到了主函数的返回类型为 integer (int main)。零表示一切顺利，一表示出了问题。

### C++ 中的输入和输出

必须包含头文件 iostream 才能使用输入/输出(CIN/库特)运算符。

[**【标准输出(cout)**](https://www.geeksforgeeks.org/basic-input-output-c/)

*   默认情况下，程序的标准输出指向屏幕。因此，通过 cout 操作符和“插入”操作符(уф)，您可以将消息打印到屏幕上。
*   要打印变量的内容，不使用双引号。
*   <
*   可以组合变量和文本:
*   cout 运算符不会在输出的末尾换行。所以如果你想打印两个句子，你必须使用新行字符(\n)。
*   可以使用 endl 操纵器代替新行字符。

下面是 C++ 程序来说明标准输出:

T3】c++ T5

```cpp
// C++ program to implement
// standard output
#include <iostream>
using namespace std;
int main()
{
  cout << "Geeks For Geeks";
  return 0;
}
```

T6T8**输出**T1

[**标准输入(cin)**](https://www.geeksforgeeks.org/basic-input-output-c/)

*   In most cases, the standard input device is the keyboard. Using cin and > > operators, you can read input from the keyboard.
*   Cin operator will always return the variable type you use with CIN. So if you ask for an integer, you will get an integer, and so on. This may cause errors when the user of the program does not return the type you expect. (For example, if you want an integer, you can get a string of characters. )
*   CIN operator is also chainable. In this case, the user must give two input values separated by any valid blank separator (tab, space or new line).

下面是 C++ 程序来说明标准输入:

T3】c++ T5

```cpp
// C++ program to implement
// standard input
#include <iostream>
using namespace std;
int main()
{
  int a;
  cout << "Enter a number" << endl;

  // User can input an integer
  cin >> a; 
  cout << "User entered number " << a << endl;
}
```

T6T8**输出**T1

### [c++ 中的数据类型](https://www.geeksforgeeks.org/c-data-types/)

数据类型是变量的声明。这决定了与变量相关联的数据的类型和大小，因为不同的数据类型占用不同大小的内存，所以知道这些变量是很重要的。

<figure class="table">T31T33】DoubleT35】Double float-pointT37】8T39T41】charT43】charchar

| **Data type** | **Meaning** | **size (bytes)** |
| --- | --- | --- |
| （同 Internationalorganizations）国际组织 | 整数 | four |
| 漂浮物 | 浮点 | four |
| 1【T46 |

</figure>

**1。int**

*   This data type is used to store integers.
*   Take up 4 bytes of memory.
*   You can store values from -2147483648 to 2147483647.

**2。浮动并加倍**

*   用于存储浮点数(小数和指数)
*   浮点的大小是 4 字节，双精度浮点的大小是 8 字节。
*   浮点用于存储最多 7 个十进制数字，而双精度用于存储最多 15 个十进制数字。
*   示例:
    *   浮点 pi = 3.14。
    *   双倍距离= 24E8 // 24 x 10 <sup>8</sup>

**3。char**

*   This data type is used to store characters.
*   Take up 1 byte of memory.
*   Characters in c++ are enclosed in single quotation marks.'' ASCII code is used to store characters in memory.
*   啁啾:char ch ='a '

**4。bool**

*   This data type has only two values: true and false.
*   Take up 1 byte of memory.
*   True means 1, false means 0.
*   Example: bool flag = false

### C++ 类型修饰符

[类型修饰符](https://www.geeksforgeeks.org/interesting-facts-about-data-types-and-modifiers-in-c-cpp/)用于修改基本数据类型。

<figure class="table">T27】无符号 int T43】长 T51】长整型 T67】长双 T75】有符号 char

| **Data type** | **Size (in bytes)** | **Meaning** |
| --- | --- | --- |
| Signed int | four | Used for integers (equivalent to int) |
| four | Only positive integers can be stored. |
| There are at least four. | Used for large integers (equivalent to long integers) |
| eight | Used for very large integers (equivalent to long integers). |
| Unsigned long integer (equivalent to unsigned long int) | eight | Used for very large positive integers or 0 |
| eight | Used for large floating-point numbers |
| one |

</figure>

下面是实现数据类型的 C++ 程序:

## c++

```cpp
// C++ program to implement
// data types
#include <iostream>
using namespace std;
int main()
{
  cout << "Size of bool is: " << 
           sizeof(bool) << 
          " bytes" << endl;
  cout << "Size of char is: " << 
           sizeof(char) << 
          " bytes" << endl;
  cout << "Size of int is: " << 
           sizeof(int) << 
          " bytes" << endl;
  cout << "Size of short int is: " << 
           sizeof(short int) << 
          " bytes" << endl;
  cout << "Size of long int is: " << 
           sizeof(long int) << 
          " bytes" << endl;
  cout << "Size of signed long int is: " << 
           sizeof(signed long int) << 
          " bytes" << endl;
  cout << "Size of unsigned long int is: " << 
           sizeof(unsigned long int) << 
          " bytes" << endl;
  cout << "Size of float is: " << 
           sizeof(float) << 
           " bytes" << endl;
  cout << "Size of double is: " << 
           sizeof(double) << 
          " bytes" << endl;
  cout << "Size of wchar_t is: " << 
           sizeof(wchar_t) << " bytes" << endl;
  return 0;
}
```

**输出**

```cpp
Size of bool is: 1 bytes
Size of char is: 1 bytes
Size of int is: 4 bytes
Size of short int is: 2 bytes
Size of long int is: 8 bytes
Size of signed long int is: 8 bytes
Size of unsigned long int is: 8 bytes
Size of float is: 4 bytes
Size of double is: 8 bytes
Size of wchar_t is: 4 bytes
```

### [派生数据类型](https://www.geeksforgeeks.org/derived-data-types-in-c/)

这些是从基本(或内置)数据类型派生的数据类型。例如数组、指针、函数、引用。

下面是实现派生数据类型的 C++ 程序:

## c++

```cpp
// C++ program to implement
// derived data types
#include <iostream>
using namespace std;

// Function definition
int sum(int n1, int n2) 
{ 
  return n1 + n2; 
}

int main()
{
  // array declaration and 
  // initialization
  int arr[5] = {2, 4, 6, 8, 10}; 
  cout << "Array elements are : ";

  for (int i = 0; i < 5; i++) 
  {
    // printing array elements
    cout << arr[i] << " "; 
  }

  // pointers
  int a = 10;

  // Declared a pointer of
  // type int
  int* p; 

  // Pointer p points the address 
  // of a
  p = &a; 
  cout << "\n" << "Value of a is " << 
           a << endl;

  // address of a will be printed
  cout << "Value of p is " << p << 
           endl; 

  // value of a will be printed
  cout << "Value of *p is " << *p << 
           endl; 

  // function calling from main
  cout << "Sum is:" << sum(5, 2) << 
           endl;

  // reference
  int x = 10;
  int& ref = x;

  // Value of x is now changed 
  // to 30
  ref = 30; 
  cout << "x = " << x << endl;

  // Value of x is now changed 
  // to 40
  x = 40; 
  cout << "ref = " << ref << endl;
  return 0;
}
```

**输出**

```cpp
Array elements are : 2 4 6 8 10 
Value of a is 10
Value of p is 0x7ffd0ec3c084
Value of *p is 10
Sum is:7
x = 30
ref = 40
```

### [用户定义的数据类型](https://www.geeksforgeeks.org/user-defined-data-types-in-c/)

这些是用户自己定义的数据类型。

例如，类、结构、联合、枚举等。

下面是实现类自定义数据类型的 C++ 程序:

## c++

```cpp
// C++ program to implement
// user-defined data types
#include <iostream>
using namespace std;
class GFG
{
  public:
  string gfg;
  void print() 
  { 
    cout << "String is: " << 
             gfg; 
  }
};

// Driver code
int main()
{
  GFG obj1;
  obj1.gfg = "GeeksForGeeks is the best Technical Website";
  obj1.print();
  return 0;
}
```

**输出**

```cpp
String is: GeeksForGeeks is the best Technical Website
```

下面是实现结构自定义数据类型的 C++ 程序:

## c++

```cpp
// C++ program to implement 
// struct 
#include <iostream>
using namespace std;

struct Geeks 
{
  int a, b;
};

// Driver code
int main()
{
  struct Geeks arr[10];
  arr[0].a = 30;
  arr[0].b = 40;
  cout << arr[0].a << ", " <<
          arr[0].b;
  return 0;
}
```

**输出**

```cpp
30, 40
```

下面是实现工会自定义数据类型的 C++ 程序:

## c++

```cpp
// C++ program to implement 
// union
#include <iostream>
using namespace std;
union gfg 
{
  int a, b;
};

// Driver code
int main()
{
  union gfg g;
  g.a = 5;
  cout << "After changing a = 5:" << 
           endl << "a = " << g.a << 
          ", b = " << g.b << endl;
  g.b = 15;
  cout << "After changing b = 15:" << 
           endl << "a = " << g.a << 
          ", b = " << g.b << endl;
  return 0;
}
```

**输出**

```cpp
After changing a = 5:
a = 5, b = 5
After changing b = 15:
a = 15, b = 15
```

下面是 C++ 程序实现枚举的数据类型:

## c++

```cpp
// C++ program to implement 
// enum
#include <iostream>
using namespace std;
enum season 
{ 
  Autmn, Spring, Winter, Summer
};

// Driver code
int main()
{
  enum season month;
  month = Summer;
  cout << month;
  return 0;
}
```

**输出**

```cpp
3
```

### [c++ 中的运算符](https://www.geeksforgeeks.org/operators-c-c/)

运算符只是告诉编译器执行某些特定操作的符号。操作员有以下几种类型–

**1。算术运算符**

算术运算符对一个或两个操作数执行一些算术运算。对一个操作数进行运算的运算符称为一元算术运算符，对两个操作数进行运算的运算符称为二元算术运算符。

*   +,-,*,/,% are binary operators.
*   +,-are unary operators.

假设:A=5，B=10

<figure class="table">相加—

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| + | Combine two operands | A+B = 15 |
| – | Slave left operand | Subtract the right operand B-A = 5 | Divide the left operand by the right operand | B/A = 2 |
| % | Find the remainder after integer division | B % A = 0 |
| + | increment | a++ = 6 |
|  |  |

</figure>

下面是实现算术运算符的 C++ 程序:

## c++

```cpp
// C++ program to implement
// arithmetic operators
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 5;
  int b = 10;

  cout << "Sum of a and b is" << 
          " " << a + b << endl;
  cout << "Difference of b and a is" << 
          " " << b - a << endl;
  cout << "Multiplication of a and b is" << 
          " " << a * b << endl;
  cout << "Division of b and a is" << 
          " " << b / a << endl;
  cout << "Modulo of b and a is" << 
          " " << b % a << endl;
  return 0;
}
```

**输出**

```cpp
Sum of a and b is 15
Difference of b and a is 5
Multiplication of a and b is 50
Division of b and a is 2
Modulo of b and a is 0
```

1.  **Pre-incrementer** : It will increment the value of the operand instantly.
2.  **Post-incrementer** : It temporarily stores the current value of the operand, and the value of the operand will be incremented only after the statement is completed.
3.  **Pre-decrementer** : immediately decrements the value of the operand.
4.  **Post-decrementer** : It temporarily stores the current value of the operand, and the value of the operand will be decremented only after the statement is completed.

下面是实现后递增器和后递减器的 C++ 程序:

T3】c++ T5

```cpp
// C++ program to implement
// post-incrementer and
// post-decrementer
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 10;
  int b;
  int c;
  b = a++ ;
  cout << a << " " <<
          b << endl;
  c = a--;
  cout << a << " " <<
          c << endl;
  return 0;
}
```

T6T8**输出**T1

下面是实现预递增器和预递减器的 C++ 程序:

T3】c++ T5

```cpp
// C++ program to implement
// pre-incrementer and 
// pre-decrementer
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 10;
  int b;
  int c;
  b = ++ a;
  cout << a << " " <<
          b << endl;
  c = --a;
  cout << a << " " <<
          c << endl;
  return 0;
}
```

T6T8**输出**T1

**2。关系运算符**

关系运算符定义两个实体之间的关系。它们给出一个布尔值作为结果，即真或假。

假设:A=5，B=10

<figure class="table">T48

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| = | True if two operands are equal | A==B is not true |
| ！= | True is given if two operands are not equal. | A！ =B is true |
| > | True if the left operand is more than the right operand. | A > B is not true |
| < | True if the left operand is less than the right operand. | A < B is true |
| >= | A > =B is not true |
| <= | True is given if the left operand is less than or equal to the right operand. | A < =B is true |

</figure>

下面是实现关系运算符的 C++ 程序:

## c++

```cpp
// C++ program to implement
// relational operators
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 5;
  int b = 10;

  if (a == b)
  {
    cout << "a==b is not equal to true" << 
             endl;
  }

  if (a != b) 
  {
    cout << "a != b is true" << 
             endl;
  }

  if (a > b)
  {
    cout << "a > b is not true" <<
             endl;
  }

  if (a < b)
  {
    cout << "a < b is true" << endl;
  }

  if (a >= b)
  {
    cout << "a >= b is not true" << 
             endl;
  }

  if (a <= b)
  {
    cout << "a <= b is true" << 
             endl;
  }
  return 0;
}
```

**输出**

```cpp
a != b is true
a < b is true
a <= b is true
```

**3。逻辑运算符**

逻辑运算符用于将多个表达式或条件连接在一起。我们有 3 个基本的逻辑运算符。

假设:A=0 且 B=1

<figure class="table">&&

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| AND operator. If both operands are non-zero values | (A&&B) is true, otherwise it is false. |
| &#124; | OR operator. If at least one of the two operands is nonzero | (A &#124;&#124; B) is true. |
| ！ | No operator. Invert the logical state of the operand. | ! One is true. |

</figure>

下面是 C++ 程序实现的逻辑运算符:

## c++

```cpp
// C++ program to implement
// the logical operators
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 0;
  int b = 1;

  if (a && b)
  {
    cout << "a && b is false" << 
             endl;
  }

  if (a || b)
  {
    cout << "a || b is true" << 
             endl;
  }

  if (!a) 
  {
    cout << "!a is true" << 
             endl;
  }
  return 0;
}
```

**输出**

```cpp
a || b is true
!a is true
```

**示例:**

*   If we need to check whether a number can be evenly divided by 2 and 3, we will use the AND operator: (num% 2 = = 0)&&num(num% 3 = = 0)
*   If this expression gives a true value, it means that num can be evenly divided by 2 and 3\. (num%2==0) || (num%3==0)
*   If this expression gives a true value, it means that num can be evenly divided by 2 or 3, or both.

**4。逐位运算符**

按位运算符是对位进行操作并执行逐位运算的运算符。

假设:A = 5(0101)和 B = 6(0110)

<figure class="table">0111t56】~t58】二进制补码。翻转钻头。

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
|  | Binary and. If there is a bit in both operands, the bit is copied to the result. | 0101&0110———0100 |
| &#124; | Binary OR. If the bit exists in any operand, the bit is copied. | 0101&#124; 0110——t41 |
| ^ | Binary XOR. If the bit is set in one operand, but not both operands, the bit is copied. | 0101^ 0110———0011 |
| ~ 0101 =>1010 |
| << | Binary left shift. The bits of the left operand are shifted to the left by the number of bits specified by the right operand. | 4(0100)4<<1= 1000 = 8 |
| >> | Binary right shift operator. The bits of the left operand are shifted to the right by the number of bits specified by the right operand. | 4>>1= 0010 = 2 |

</figure>

如果对数字 n 应用移位运算符，则

下面是实现按位运算符的 C++ 程序:

## c++

```cpp
// C++ program to implement
// bitwise operators
#include <iostream>
using namespace std;

// Driver code
int main()
{
  // Binary representation 
  // of 5 is 0101
  int a = 5; 

  // Binary representation 
  // of 6 is 0110
  int b = 6; 
  cout << (a & b) << endl;
  cout << (a | b) << endl;
  cout << (a ^ b) << endl;
  cout << (a << 1) << endl;
  cout << (a >> 1) << endl;

  return 0;
}
```

**输出**

```cpp
4
7
3
10
2
```

**5。赋值运算符**

<figure class="table">

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| = | Assign the value of the right operand to the left operand. | A = B will put the value of B in A |
| += | The result of adding the right operand to the left operand and assigning the left operand. | A+=B means A = A+B |
| -= | Subtract the right operand from the left operand and assign the result to the left operand. | A-= B means A = A-B |
| * = | Multiply the right operand with the left operand and assign the result to the left operand. | A*=B means A = A * B |
| /= | Divide the left operand by the right operand and assign the result to the left operand. | A/= B means A = A/B |

</figure>

下面是实现赋值运算符的 C++ 程序:

## c++

```cpp
// C++ program to implement
// assignment operator
#include <iostream>
using namespace std;

// Driver code
int main()
{
  // a is assigned value 5
  int a = 5; 

  // a becomes 5
  cout << a << endl; 

  // this is same as a=a+2
  a += 2; 

  // a becomes 5+2 =7
  cout << a << endl; 

  // this is same as a=a-2
  a -= 2; 

  // a becomes 7-2 =5
  cout << a << endl; 

  // this is same as a=a*2
  a *= 2; 

  // a becomes 5*2 =10
  cout << a << endl; 

  // this is same as a=a/2
  a /= 2; 

  // a becomes 10/2 =5
  cout << a << endl; 

  return 0;
}
```

**输出**

```cpp
5
7
5
10
5
```

**6。Misc 运算符**

<figure class="table">

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| sizeof() | Returns the size of a variable. | If a is an integer, sizeof(a) will return 4\. |
| What's your condition? X: y | conditional operator. If the condition is true, the value of x is returned; otherwise, the value of y is returned. | A+= B means A = A+B |
| cast | casting operator will convert one data type to another | int (4.350) will return 4\. |
| Comma (, | Comma operator causes a series of operations to be performed. The value of the whole comma expression is the value of the last expression of the comma-separated list. |  |

</figure>

下面是实现杂运算符的 C++ 程序:

## c++

```cpp
// C++ program to implement
// miscellaneous operator
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int a = 4;

  // sizeof () returns the size
  // of variable in bytes
  cout << sizeof(a) << endl;   

  int x = 5;
  int y = 8;

  // ternary or conditional operator
  int min = x < y ? x : y;
  cout << "Minimum value from x and y is " <<
           min << endl;

  // casting from float to int
  cout << int(4.350) << endl; 

  // comma operator is used for
  int d = 2, b = 3, c = 4; 

  // multiple declarations
  cout << d << " " << b << " " << 
          c << " " << endl;
  return 0;
}
```

**输出**

```cpp
4
Minimum value from x and y is 5
4
2 3 4 
```

### 运算符的优先级

<figure class="table"><<>T129= :

| **类别** | **操作员** | **结合律** |
| --- | --- | --- |
| 后缀 | () [] - >。+ — | 从左到右 |
| 一元 | +—！~ ++ __(类型)* & sizeof | 右向左 |
| 乘法 | * / % | 左向右 |
| 加法 | +– | 左向右 |
| 移位 | 从左到右 |
| 按位与 | & | 从左到右 |
| 按位异或 | ^ | 从左到右 |
| 按位或 | &#124; | 从右向左 |
| 赋值 | =+=-=/= % =>>=<<=&= ^= &#124; = | 从右向左 |
| 逗号 | 、 | 从左向右 |

</figure>

### [决策](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/)

**1。如果/否则**

if 块用于指定要执行的代码。如果其中指定的条件为真，则否则执行 else 块。下面是实现 if-else 的 C++ 程序:

## C++

```cpp
// C++ program to implement
// if-else
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int age;
  cin >> age;

  if (age >= 18) 
  {
    cout << "You can vote.";
  }
  else 
  {
    cout << "Not eligible for voting.";
  }

  return 0;
}
```

**Output**

```cpp
Not eligible for voting.
```

**2。否则如果**

要指定多个 if 条件，我们首先使用 if，然后连续语句使用 else if。下面是实现 else if 的 C++ 程序:

## c++

```cpp
// C++ program to implement
// else if
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int x, y;
  cin >> x >> y;
  if (x == y) 
  {
    cout << "Both the numbers are equal";
  }
  else if (x > y) 
  {
    cout << "X is greater than Y";
  }
  else 
  {
    cout << "Y is greater than X";
  }
  return 0;
}
```

**输出**

```cpp
Y is greater than X
```

**3。嵌套 if**

为了在条件中指定条件，我们使用嵌套的 if。下面是 C++ 程序实现嵌套 if:

## c++

```cpp
// C++ program to implement
// nested if
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int x, y;
  cin >> x >> y;

  if (x == y) 
  {
    cout << "Both the numbers are equal";
  }
  else 
  {
    if (x > y) 
    {
      cout << "X is greater than Y";
    }
    else 
    {
      cout << "Y is greater than X";
    }
  }
  return 0;
}
```

**输出**

```cpp
Y is greater than X
```

**4。** [**切换语句**](https://www.geeksforgeeks.org/switch-statement-cc/)

Switch case 语句可以替代将一个变量与多个值进行比较的 long if 语句。找到匹配后，它会执行该值大小写的相应代码。

**语法:**

```cpp
switch (n)
{
  case 1:     // code to be executed if n == 1;
  break;
  case 2:    // code to be executed if n == 2;
  break;
  default:   // code to be executed if n doesn't match any of the above cases
} 
```

*   开关中的变量应该有一个常量值。
*   break 语句是可选的。它终止 switch 语句，并将控制移到 switch 之后的下一行。
*   如果没有添加 break 语句，开关不会被终止，它将继续到开关之后的下一行。
*   每个案例值都应该是唯一的。
*   默认情况下是可选的。但是它很重要，因为它是在没有匹配的案例值时执行的。

使用 Switch 语句的基本计算器:

## c++

```cpp
// C++ program to implement
// the switch statement
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int n1, n2;
  char op;
  cout << "Enter 2 numbers: ";
  cin >> n1 >> n2;
  cout << "Enter operand: ";
  cin >> op;

  switch (op)
  {
    case '+':
      cout << n1 + n2 << endl;
      break;
    case '-':
      cout << n1 - n2 << endl;
      break;
    case '*':
      cout << n1 * n2 << endl;
      break;
    case '/':
      cout << n1 / n2 << endl;
      break;
    case '%':
      cout << n1 % n2 << endl;
      break;

    default:
      cout << "Operator not found!" << 
               endl;
      break;
  }

  return 0;
}
```

**输出**

```cpp
Enter 2 numbers: Enter operand: Operator not found!
```

### [c++ 中的循环](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)

循环用于重复执行语句块，直到满足特定条件。循环由初始化语句、测试条件和增量语句组成。

**1。对于回路**

for 循环的语法是

```cpp
for (initialization; condition; update)
{
   // body of-loop
}
```

下面是实现 for 循环的 C++ 程序:

## c++

```cpp
// C++ program to implement
// for loop
#include <iostream>
using namespace std;

// Driver code
int main()
{
  for (int i = 1; i <= 5; i++) 
  {
    cout << i << " ";
  }
  return 0;
}
```

**输出**

```cpp
1 2 3 4 5 
```

**说明:**

for 循环由值 1 初始化，测试条件为 i<=5，即循环一直执行到 I 的值保持小于或等于 5。在每次迭代中，通过执行 i++，I 的值增加 1。

**2。边循环**

while 循环的语法是

```cpp
while (condition) 
{
 // body of the loop
}
```

下面是 C++ 程序实现的 while 循环:

T3】c++ T5

```cpp
// C++ program to implement
// while loop
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int i = 1;
  while (i <= 5) 
  {
    cout << i << " ";
    i++ ;
  }
  return 0;
}
```

T6T8**输出**T1

**说明:**

while 循环由值 1 初始化，测试条件为 i<=5，即循环一直执行到 I 的值保持小于或等于 5。在每次迭代中，通过执行 i++，I 的值增加 1。

**3。do͙一边循环**

while 循环的语法是

```cpp
do {
// body of loop;
}
while (condition);
```

下面是实现边做边循环的 C++ 程序:

T3】c++ T5

```cpp
// C++ program to implement
// do-while loop
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int i = 1;
  do {
    cout << i << " ";
    i++ ;
  } while (i <= 5);
  return 0;
}
```

T6T8**输出**T1

**说明:**

do-while 循环变量由值 1 初始化，在每次迭代中，I 的值通过执行 i++ 而增加 1，测试条件是 i<=5，即循环一直执行到 I 的值保持小于或等于 5。由于测试条件只在循环运行一次后检查，所以边做边循环至少运行一次。

### 循环跳跃

循环中的跳转用于控制循环的流动。有两种语句用于实现循环中的跳转——继续和中断。当我们需要在满足某个特定条件时改变循环的流程时，就会用到这些语句。

**1。** [**继续**](https://www.geeksforgeeks.org/continue-statement-cpp/)

continue 语句用于跳到该循环的下一次迭代。这意味着它会停止循环的一次迭代。该循环中 continue 语句之后的所有语句都不会执行。

下面是实现 Continue 语句的 C++ 程序:

T3】c++ T5

```cpp
// C++ program to implement
// the continue statement
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int i;
  for (i = 1; i <= 20; i++) 
  {
    if (i % 3 == 0) 
    {
      continue;
    }
    cout << i << endl;
  }
}
```

T6T8**输出**T1

**说明:**

在这个 for 循环中，只要 I 是一个可被 3 整除的数，它就不会被打印，因为由于 continue 语句，循环将跳到下一个迭代。因此，除了能被 3 整除的数字之外，所有的数字都会被打印出来。

**2。** [**破**](https://www.geeksforgeeks.org/break-statement-cc/)

break 语句用于终止当前循环。一旦在循环中遇到 break 语句，循环的所有后续迭代都将停止，控制将转移到循环结束后的第一条语句。

下面是实现 break 语句的 C++ 程序:

## c++

```cpp
// C++ program to implement
// the break statement
#include <iostream>
using namespace std;

// Driver code
int main()
{
  int i;
  for (i = 1; i <= 20; i++) 
  {
    if (i == 11) 
    {
      break;
    }
    cout << i << endl;
  }
}
```

**输出**

```cpp
1
2
3
4
5
6
7
8
9
10
```

**说明:**

在这个循环中，当 I 等于 11 时，for 循环由于 break 语句而终止，因此，程序将只打印从 1 到 10 的数字。