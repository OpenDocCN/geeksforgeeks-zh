# C 中的基本输入输出

> 原文:[https://www.geeksforgeeks.org/basic-input-and-output-in-c/](https://www.geeksforgeeks.org/basic-input-and-output-in-c/)

c 语言有允许程序输入和输出的标准库。C 语言中的 **stdio.h** 或**标准输入输出库**，有输入输出的方法。

### scanf()

C 语言中的 scanf()方法根据指定的类型从控制台读取值。

**语法:**

> **扫描(“%X”，&变量 ofxttype)；**
> 
> 其中 **%X** 是 C 中的[格式说明符。这是一种告诉编译器变量中数据类型的方法](https://www.geeksforgeeks.org/format-specifiers-in-c/)
> 
> 和
> 
> **&** 是 C 语言中的地址运算符，它告诉编译器改变这个变量的真实值，存储在内存中的这个地址。

### printf()

C 语言中的 printf()方法在控制台屏幕上打印作为参数传递给它的值。

**语法:**

> **printf("%X "，变量 ofxttype)；**
> 
> 其中 **%X** 是 C 中的[格式说明符。这是一种告诉编译器变量中数据类型的方法](https://www.geeksforgeeks.org/format-specifiers-in-c/)
> 
> 和
> 
> **&** 是 C 语言中的地址运算符，它告诉编译器改变这个变量的真实值，存储在内存中的这个地址。

### C 语言中基本类型的输入输出怎么取？

C 语言中的基本类型包括 int、float、char 等类型。为了输入或输出特定类型，上述语法中的 **X** 用该类型的特定格式说明符进行了更改。

输入和输出的语法如下:

*   **整数:**

    ```cpp
    Input: scanf("%d", &intVariable);
    Output: printf("%d", intVariable);

    ```

*   **浮动:**T0】
*   **人物:**

    ```cpp
    Input: scanf("%c", &charVariable);
    Output: printf("%c", charVariable);

    ```

更多例子请参考 C 中的[格式说明符。](https://www.geeksforgeeks.org/format-specifiers-in-c/)

```cpp
// C program to show input and output

#include <stdio.h>

int main()
{

    // Declare the variables
    int num;
    char ch;
    float f;

    // --- Integer ---

    // Input the integer
    printf("Enter the integer: ");
    scanf("%d", &num);

    // Output the integer
    printf("\nEntered integer is: %d", num);

    // --- Float ---

    // Input the float
    printf("\n\nEnter the float: ");
    scanf("%f", &f);

    // Output the float
    printf("\nEntered float is: %f", f);

    // --- Character ---

    // Input the Character
    printf("\n\nEnter the Character: ");
    scanf("%c", &ch);

    // Output the Character
    printf("\nEntered integer is: %c", ch);

    return 0;
}
```

**Output:**

```cpp
Enter the integer: 10
Entered integer is: 10

Enter the float: 2.5
Entered float is: 2.500000

Enter the Character: A
Entered Character is: A

```

### 如何在 C 语言中取高级类型的输入输出？

C 语言中的高级类型包括像 String 这样的类型。为了输入或输出字符串类型，上述语法中的 **X** 用 **%s** 格式说明符进行了更改。

字符串输入和输出的语法是:

```cpp
Input: scanf("%s", stringVariable);
Output: printf("%s", stringVariable);

```

**示例:**

```cpp
// C program to show input and output

#include <stdio.h>

int main()
{

    // Declare string variable
    // as character array
    char str[50];

    // --- String ---
    // To read a word

    // Input the Word
    printf("Enter the Word: ");
    scanf("%s\n", str);

    // Output the Word
    printf("\nEntered Word is: %s", str);

    // --- String ---
    // To read a Sentence

    // Input the Sentence
    printf("\n\nEnter the Sentence: ");
    scanf("%[^\n]\ns", str);

    // Output the String
    printf("\nEntered Sentence is: %s", str);

    return 0;
}
```

**Output:**

```cpp
Enter the Word: GeeksForGeeks
Entered Word is: GeeksForGeeks

Enter the Sentence: Geeks For Geeks
Entered Sentence is: Geeks For Geeks

```

**Related Articles:**[Format specifiers in C](https://www.geeksforgeeks.org/format-specifiers-in-c/)[Use of fflush(stdin) in C](https://www.geeksforgeeks.org/use-fflushstdin-c/)[Clearing The Input Buffer In C/C++ ](https://www.geeksforgeeks.org/clearing-the-input-buffer-in-cc/)