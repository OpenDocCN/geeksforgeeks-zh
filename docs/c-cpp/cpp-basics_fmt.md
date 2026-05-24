# C++ 基础知识

> 原文：[https://www.geeksforgeeks.org/cpp-basics/](https://www.geeksforgeeks.org/cpp-basics/)

C++ 是一种跨平台语言，可用于创建高性能应用程序。它是由比雅尼·斯特劳斯特鲁普开发的，是 C 语言的扩展。该语言在 2011 年、2014 年和 2017 年进行了 3 次重大更新，分别为 C++ 11、C++ 14 和 C++ 17。

## 为什么要用 C++？

*   C++ 是世界上最流行的编程语言之一。
*   C++ 可以在今天的操作系统、图形用户界面和嵌入式系统中找到。
*   C++ 是一种面向对象的编程语言，它为程序提供了清晰的结构，并允许代码被重用，从而降低了开发成本。
*   C++ 是可移植的，可以用来开发适用于多个平台的应用程序。
*   C++ 有趣又易学！
*   由于 C++ 接近 C# 和 Java，所以程序员很容易切换到 C++ 或者相反。

## C++ 基础程序

### C++

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

### C++ 代码的组件：

1.  **【评论】**：这两个斜杠（`//`）符号是用来在程序中添加评论的。它对程序的行为或结果没有任何影响。它用来描述你正在编写的程序。
2.  `#include<iostream>`：`#include` 是用于在我们的程序中包含文件的预处理器指令。这里我们包含了 `iostream` 标准文件，这是在 C++ 中声明基本标准输入/输出库所必需的。
3.  `using namespace std;`：标准 C++ 库的所有元素都在一个命名空间中声明。这里我们使用的是 `std` 命名空间。
4.  `int main()`：任何 C++ 程序的执行都是从 `main` 函数开始的，因此在你的程序中有一个 `main` 函数是必要的。“int”是此函数的返回值。（我们稍后将更详细地研究函数）。
5.  `{}`：花括号用来表示任何函数的起点和终点。每个开口支架都应该有一个相应的封闭支架。
6.  `cout << "Hello World!\n";`：这是 C++ 语句。`cout` 表示 C++ 中的标准输出流。它在标准命名空间内的 `iostream` 标准文件中声明。报价之间的文本将打印在屏幕上。`\n` 不会打印，它用于添加换行符。C++ 中的每个语句都以分号（`;`）结束。
7.  `return 0;`：`return` 表示函数结束。这里的函数是 `main`，所以当我们按 `return 0` 时，它退出程序。我们返回 0 是因为我们提到了主函数的返回类型为 integer（`int main`）。零表示一切顺利，一表示出了问题。

## C++ 中的输入和输出

必须包含头文件 `iostream` 才能使用输入/输出（`cin`/`cout`）运算符。

### 【标准输出（cout）】

*   默认情况下，程序的标准输出指向屏幕。因此，通过 `cout` 操作符和“插入”操作符（`<<`），您可以将消息打印到屏幕上。
*   要打印变量的内容，不使用双引号。
*   `cout` 可以组合变量和文本。
*   `cout` 运算符不会在输出的末尾换行。所以如果你想打印两个句子，你必须使用新行字符（`\n`）。
*   可以使用 `endl` 操纵器代替新行字符。

下面是 C++ 程序来说明标准输出：

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

**输出**

### 【标准输入（cin）】

*   在大多数情况下，标准输入设备是键盘。使用 `cin` 和 `>>` 运算符，您可以从键盘读取输入。
*   `cin` 运算符将始终返回您与 `cin` 一起使用的变量类型。所以如果你要求一个整数，你将得到一个整数，依此类推。当程序的用户没有返回您期望的类型时，这可能会导致错误。（例如，如果您想要一个整数，您可能会得到一个字符串。）
*   `cin` 运算符也是可链接的。在这种情况下，用户必须给出两个输入值，由任何有效的空白分隔符（制表符、空格或换行符）分隔。

下面是 C++ 程序来说明标准输入：

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

**输出**

## C++ 中的数据类型

数据类型是变量的声明。这决定了与变量相关联的数据的类型和大小，因为不同的数据类型占用不同大小的内存，所以知道这些变量是很重要的。

| **Data type** | **Meaning** | **size (bytes)** |
| --- | --- | --- |
| `int` | 整数 | 4 |
| `float` | 浮点 | 4 |
| `double` | 双精度浮点 | 8 |
| `char` | 字符 | 1 |

### 1. `int`

*   此数据类型用于存储整数。
*   占用 4 字节内存。
*   您可以存储从 -2147483648 到 2147483647 的值。

### 2. `float` 和 `double`

*   用于存储浮点数（小数和指数）。
*   `float` 的大小是 4 字节，`double` 的大小是 8 字节。
*   `float` 用于存储最多 7 个十进制数字，而 `double` 用于存储最多 15 个十进制数字。
*   示例：
    *   `float pi = 3.14;`
    *   `double distance = 24E8; // 24 x 10^8`

### 3. `char`

*   此数据类型用于存储字符。
*   占用 1 字节内存。
*   C++ 中的字符用单引号括起来。`' '`。ASCII 码用于在内存中存储字符。
*   示例：`char ch = 'a';`

### 4. `bool`

*   此数据类型只有两个值：`true` 和 `false`。
*   占用 1 字节内存。
*   `true` 表示 1，`false` 表示 0。
*   示例：`bool flag = false;`

## C++ 类型修饰符

[类型修饰符](https://www.geeksforgeeks.org/interesting-facts-about-data-types-and-modifiers-in-c-cpp/)用于修改基本数据类型。

| **Data type** | **Size (in bytes)** | **Meaning** |
| --- | --- | --- |
| `signed int` | 4 | 用于整数（等同于 `int`） |
| `unsigned int` | 4 | 只能存储正整数。 |
| `long int` | 至少 4 | 用于大整数（等同于 `long`） |
| `long long int` | 8 | 用于非常大的整数（等同于 `long long`）。 |
| `unsigned long int` | 8 | 用于非常大的正整数或 0 |
| `long double` | 8 | 用于大型浮点数 |
| `signed char` | 1 | 用于字符 |

下面是实现数据类型的 C++ 程序：

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

## 派生数据类型

这些是从基本（或内置）数据类型派生的数据类型。例如数组、指针、函数、引用。

下面是实现派生数据类型的 C++ 程序：

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

## 用户定义的数据类型

这些是用户自己定义的数据类型。

例如，类、结构、联合、枚举等。

下面是实现类自定义数据类型的 C++ 程序：

## C++ 用户自定义数据类型

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

```

## C++ 运算符

运算符只是告诉编译器执行某些特定操作的符号。操作员有以下几种类型–

### 1. 算术运算符

算术运算符对一个或两个操作数执行一些算术运算。对一个操作数进行运算的运算符称为一元算术运算符，对两个操作数进行运算的运算符称为二元算术运算符。

*   `+`, `-`, `*`, `/`, `%` 是二元运算符。
*   `+`, `-` 是一元运算符。

假设: `A = 5`，`B = 10`

| **Operator** | **operation** | **Example** |
| :--- | :--- | :--- |
| `+` | Combine two operands | `A + B = 15` |
| `-` | Subtract the right operand from the left operand | `B - A = 5` |
| `/` | Divide the left operand by the right operand | `B / A = 2` |
| `%` | Find the remainder after integer division | `B % A = 0` |
| `++` | increment | `a++ = 6` |

下面是实现算术运算符的 C++ 程序:

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

**输出**

下面是实现预递增器和预递减器的 C++ 程序:

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

**输出**

### 2. 关系运算符

关系运算符定义两个实体之间的关系。它们给出一个布尔值作为结果，即真或假。

假设: `A = 5`，`B = 10`

| **Operator** | **operation** | **Example** |
| :--- | :--- | :--- |
| `==` | True if two operands are equal | `A == B` is not true |
| `!=` | True is given if two operands are not equal. | `A != B` is true |
| `>` | True if the left operand is more than the right operand. | `A > B` is not true |
| `<` | True if the left operand is less than the right operand. | `A < B` is true |
| `>=` | True if the left operand is greater than or equal to the right operand. | `A >= B` is not true |
| `<=` | True is given if the left operand is less than or equal to the right operand. | `A <= B` is true |

下面是实现关系运算符的 C++ 程序:

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

### 3. 逻辑运算符

逻辑运算符用于将多个表达式或条件连接在一起。我们有 3 个基本的逻辑运算符。

假设: `A = 0` 且 `B = 1`

| **Operator** | **operation** | **Example** |
| :--- | :--- | :--- |
| `&&` | AND operator. If both operands are non-zero values | `(A && B)` is true, otherwise it is false. |
| `\|\|` | OR operator. If at least one of the two operands is nonzero | `(A \|\| B)` is true. |
| `!` | No operator. Invert the logical state of the operand. | `!A` is true. |

下面是 C++ 程序实现的逻辑运算符:

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

*   If we need to check whether a number can be evenly divided by 2 and 3, we will use the AND operator: `(num % 2 == 0) && (num % 3 == 0)`
*   If this expression gives a true value, it means that `num` can be evenly divided by 2 and 3. `(num % 2 == 0) || (num % 3 == 0)`
*   If this expression gives a true value, it means that `num` can be evenly divided by 2 or 3, or both.

### 4. 逐位运算符

按位运算符是对位进行操作并执行逐位运算的运算符。

假设: `A = 5 (0101)` 和 `B = 6 (0110)`

| **Operator** | **operation** | **Example** |
| :--- | :--- | :--- |
| `&` | Binary and. If there is a bit in both operands, the bit is copied to the result. | `0101 & 0110` — `0100` |
| `\|` | Binary OR. If the bit exists in any operand, the bit is copied. | `0101 \| 0110` — `0111` |
| `^` | Binary XOR. If the bit is set in one operand, but not both operands, the bit is copied. | `0101 ^ 0110` — `0011` |
| `~` | Binary NOT. It is unary and has the effect of 'flipping' bits. | `~0101` => `1010` |
| `<<` | Binary left shift. The bits of the left operand are shifted to the left by the number of bits specified by the right operand. | `4 (0100) << 1 = 1000 = 8` |
| `>>` | Binary right shift operator. The bits of the left operand are shifted to the right by the number of bits specified by the right operand. | `4 >> 1 = 0010 = 2` |

如果对数字 `n` 应用移位运算符，则

下面是实现按位运算符的 C++ 程序:

## C++

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

```

## 5. 赋值运算符

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| `=` | Assign the value of the right operand to the left operand. | `A = B` will put the value of `B` in `A` |
| `+=` | The result of adding the right operand to the left operand and assigning the left operand. | `A+=B` means `A = A+B` |
| `-=` | Subtract the right operand from the left operand and assign the result to the left operand. | `A-= B` means `A = A-B` |
| `*=` | Multiply the right operand with the left operand and assign the result to the left operand. | `A*=B` means `A = A * B` |
| `/=` | Divide the left operand by the right operand and assign the result to the left operand. | `A/= B` means `A = A/B` |

下面是实现赋值运算符的 C++ 程序:

## C++

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

```

## 6. Misc 运算符

| **Operator** | **operation** | **Example** |
| --- | --- | --- |
| `sizeof()` | Returns the size of a variable. | If `a` is an integer, `sizeof(a)` will return 4. |
| `? :` | conditional operator. If the condition is true, the value of x is returned; otherwise, the value of y is returned. | `A+= B` means `A = A+B` |
| `cast` | casting operator will convert one data type to another | `int (4.350)` will return 4. |
| `,` | Comma operator causes a series of operations to be performed. The value of the whole comma expression is the value of the last expression of the comma-separated list. |  |

下面是实现杂运算符的 C++ 程序:

## C++

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
Minimum value from x and y is 5

2 3 4 
```

### 运算符的优先级

| **类别** | **运算符** | **结合律** |
| --- | --- | --- |
| 后缀 | `() [] -> . ++ --` | 从左到右 |
| 一元 | `+ - ! ~ ++ -- (type)* & sizeof` | 右向左 |
| 乘法 | `* / %` | 左向右 |
| 加法 | `+ -` | 左向右 |
| 移位 | `<< >>` | 从左到右 |
| 按位与 | `&` | 从左到右 |
| 按位异或 | `^` | 从左到右 |
| 按位或 | `|` | 从右向左 |
| 赋值 | `= += -= *= /= %=>>= <<= &= ^= |=` | 从右向左 |
| 逗号 | `,` | 从左向右 |

### 决策

## 1. if/else

`if` 块用于指定要执行的代码。如果其中指定的条件为真，则执行 `if` 块，否则执行 `else` 块。下面是实现 `if-else` 的 C++ 程序:

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

## 2. else if

要指定多个 `if` 条件，我们首先使用 `if`，然后连续语句使用 `else if`。下面是实现 `else if` 的 C++ 程序:

## C++

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

## 3. 嵌套 if

为了在条件中指定条件，我们使用嵌套的 `if`。下面是 C++ 程序实现嵌套 `if`:

## C++

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

## 4. switch 语句

`Switch case` 语句可以替代将一个变量与多个值进行比较的长 `if` 语句。找到匹配后，它会执行该值大小写的相应代码。

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

*   `switch` 中的变量应该有一个常量值。
*   `break` 语句是可选的。它终止 `switch` 语句，并将控制移到 `switch` 之后的下一行。
*   如果没有添加 `break` 语句，`switch` 不会被终止，它将继续到 `switch` 之后的下一行。
*   每个 `case` 值都应该是唯一的。
*   `default` 是可选的。但是它很重要，因为它是在没有匹配的 `case` 值时执行的。

使用 `Switch` 语句的基本计算器:

## C++

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

### c++ 中的循环

循环用于重复执行语句块，直到满足特定条件。循环由初始化语句、测试条件和增量语句组成。

## 1. for 循环

`for` 循环的语法是

```cpp
for (initialization; condition; update)
{
   // body of-loop
}
```

下面是实现 `for` 循环的 C++ 程序:

# C++

## For 循环

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

`for` 循环由值 `1` 初始化，测试条件为 `i<=5`，即循环一直执行到 `i` 的值保持小于或等于 `5`。在每次迭代中，通过执行 `i++`，`i` 的值增加 `1`。

## While 循环

`while` 循环的语法是

```cpp
while (condition) 
{
 // body of the loop
}
```

下面是 C++ 程序实现的 `while` 循环:

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

**输出**

**说明:**

`while` 循环由值 `1` 初始化，测试条件为 `i<=5`，即循环一直执行到 `i` 的值保持小于或等于 `5`。在每次迭代中，通过执行 `i++`，`i` 的值增加 `1`。

## Do-While 循环

`do-while` 循环的语法是

```cpp
do {
// body of loop;
}
while (condition);
```

下面是实现 `do-while` 循环的 C++ 程序:

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

**输出**

**说明:**

`do-while` 循环变量由值 `1` 初始化，在每次迭代中，`i` 的值通过执行 `i++` 而增加 `1`，测试条件是 `i<=5`，即循环一直执行到 `i` 的值保持小于或等于 `5`。由于测试条件只在循环运行一次后检查，所以 `do-while` 循环至少运行一次。

### 循环跳跃

循环中的跳转用于控制循环的流动。有两种语句用于实现循环中的跳转——`continue` 和 `break`。当我们需要在满足某个特定条件时改变循环的流程时，就会用到这些语句。

#### 1. Continue

`continue` 语句用于跳到该循环的下一次迭代。这意味着它会停止循环的一次迭代。该循环中 `continue` 语句之后的所有语句都不会执行。

下面是实现 `continue` 语句的 C++ 程序:

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

**输出**

**说明:**

在这个 `for` 循环中，只要 `i` 是一个可被 `3` 整除的数，它就不会被打印，因为由于 `continue` 语句，循环将跳到下一个迭代。因此，除了能被 `3` 整除的数字之外，所有的数字都会被打印出来。

#### 2. Break

`break` 语句用于终止当前循环。一旦在循环中遇到 `break` 语句，循环的所有后续迭代都将停止，控制将转移到循环结束后的第一条语句。

下面是实现 `break` 语句的 C++ 程序:

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

**说明:**

在这个循环中，当 `i` 等于 `11` 时，`for` 循环由于 `break` 语句而终止，因此，程序将只打印从 `1` 到 `10` 的数字。