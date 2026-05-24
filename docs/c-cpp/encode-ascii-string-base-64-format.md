# 将 ASCII 字符串编码为 Base-64 格式

> 原文:[https://www . geesforgeks . org/encode-ascii-string-base-64-format/](https://www.geeksforgeeks.org/encode-ascii-string-base-64-format/)

Base 64 是一种将二进制数据转换成文本格式的编码方案，这样编码的文本数据可以很容易地在网络上传输而不被破坏，并且没有任何数据丢失。Base64 常用于许多应用程序，包括通过 MIME 发送电子邮件和以 XML 存储复杂数据。
向网络发送正常二进制数据的问题是，比特可能被底层协议误解，在接收节点产生不正确的数据，这就是我们使用该代码的原因。

**为什么是 64 号基地？**

对我们的数据进行编码后得到的文本具有广泛存在于许多字符集中的字符，因此数据被破坏或修改的可能性非常小。

**如何转换成 base 64 格式？**

base64 中的字符集是

```cpp
char_set = "ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz0123456789+/" 
// 64 characters
```

**基本思路**

举个例子。我们必须将字符串“MENON”编码成 base64 格式。让我们称“MENON”为 **input_str** ，高于 base64 字符集(“ABC..+/)作为 **char_set** ，结果编码字符串作为 **res_str** 。

1.  从 **input_str** 中取 3 个字符，即“MEN”，因为每个字符大小是 8 位，所以我们会有(8 * 3) 24 位。
2.  将它们分组为每个 6 位的块(24 / 6 = 4 个块)。(为什么是 6？)因为 2^6 = 64 个字符，用 6 位我们可以表示 **char_set** 中的每个字符。
3.  将每个 6 位数据块转换为相应的十进制值。获得的十进制值是 **char_set** 中结果编码字符的索引。
4.  所以从**输入的每 3 个字符，我们将在 **res_str** 中收到 4 个字符。**
5.  如果我们在 **input_str** 中剩下的字符少于 3 个，即“开”，该怎么办。我们有 16 位，块将是 16 / 6 = 2 块。最右边的 4 位不能构成一个合适的块(1 个块= 6 位)，因此我们在块的右侧附加零，使其成为一个合适的块，即在右侧附加 2 个零。现在我们有 3 个合适的块，找到每个块对应的十进制值，得到索引。
6.  由于**输入字符串**中少于 3 个字符(“开”)，我们将在 res_str 中追加“=”。例如，在 **res_str** 中，3–2 = 1 个“=”的填充。

**例**

1.将“MENON”转换为其(8 位)二进制状态格式。获取字符串的每个字符，并写出其 8 位二进制表示。
待编码字符串中字符的 ASCII 值

```cpp
M : 77 (01001101), E : 69 (01000101), 
N : 78 (01001110), O : 79 (01001111), N : 78 (01001110)
```

上述字符串的合成二进制数据为:

```cpp
01001101 01000101 01001110 01001111 01001110
```

2.从左边开始制作 **6** 位的块，直到所有位都被覆盖
位流:

```cpp
(010011) (010100) (010101) (001110) (010011) (110100) (1110)
```

3.如果最右边的块少于 6 位，只需在该块的右边添加 0，使其为 6 位。在上面的例子中，我们必须加上 2 个零，使它变成 6。
比特流:

```cpp
(010011) (010100) (010101) (001110) (010011) (110100) (111000)
```

请注意粗体零。
4。从 input _ str(“MEN”)中提取 3 个字符，即 24 位，并找到相应的十进制值(char_set 的索引)。
街区:

```cpp
INDEX --> (010011) : 19, (010100) : 20, (010101) : 21, (001110) : 14
char_set[19] = T, char_set[20] = U, char_set[21] = V, char_set[14] = O
```

所以我们的 input _ str =“MEN”将被转换为编码字符串“TUVO”。
5。取剩余字符(“开”)。我们必须用 1 "= "填充结果编码字符串，因为 input_str 中的字符数小于 3。(3–2 = 1 个填充)
区块:

```cpp
INDEX --> (010011) : 19 (110100) : 52 (111000) : 56
char_set[19] = T char_set[52] = 0 char_set[56] = 4
So our input_str = "ON" will be converted to encoded string "T04=".
```

示例:

```cpp
Input : MENON // string in ASCII
Output :TUVOT04= // encoded string in Base 64.

Input : geeksforgeeks
Output : Z2Vla3Nmb3JnZWVrcw==
```

 **Approach** :

我们可以使用按位运算符对字符串进行编码。我们可以取一个整数“val”(在大多数编译器上通常是 4 字节)，并将 input_str 的所有字符(一次 3 个)存储在 val 中。input_str 中的字符将以位的形式存储在 val
中。我们将使用(或运算符)来存储字符，并将(左–SHIFT)乘以 8，以便
为另外 8 位腾出空间。以类似的方式，我们将使用(右移)一次从值 6 中检索位
，并通过对 63 (111111)执行&来找到位的值，这将为我们提供索引。然后我们可以通过查 char_set 的索引得到结果字符。

## C++

```cpp
// C++ program to encode an ASCII
// string in Base64 format
#include <iostream>
using namespace std;
#define SIZE 1000

// Takes string to be encoded as input
// and its length and returns encoded string
char* base64Encoder(char input_str[], int len_str)
{

    // Character set of base64 encoding scheme
    char char_set[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";

    // Resultant string
    char *res_str = (char *) malloc(SIZE * sizeof(char));

    int index, no_of_bits = 0, padding = 0, val = 0, count = 0, temp;
    int i, j, k = 0;

    // Loop takes 3 characters at a time from
    // input_str and stores it in val
    for (i = 0; i < len_str; i += 3)
        {
            val = 0, count = 0, no_of_bits = 0;

            for (j = i; j < len_str && j <= i + 2; j++)
            {
                // binary data of input_str is stored in val
                val = val << 8;

                // (A + 0 = A) stores character in val
                val = val | input_str[j];

                // calculates how many time loop
                // ran if "MEN" -> 3 otherwise "ON" -> 2
                count++ ;

            }

            no_of_bits = count * 8;

            // calculates how many "=" to append after res_str.
            padding = no_of_bits % 3;

            // extracts all bits from val (6 at a time)
            // and find the value of each block
            while (no_of_bits != 0)
            {
                // retrieve the value of each block
                if (no_of_bits >= 6)
                {
                    temp = no_of_bits - 6;

                    // binary of 63 is (111111) f
                    index = (val >> temp) & 63;
                    no_of_bits -= 6;        
                }
                else
                {
                    temp = 6 - no_of_bits;

                    // append zeros to right if bits are less than 6
                    index = (val << temp) & 63;
                    no_of_bits = 0;
                }
                res_str[k++ ] = char_set[index];
            }
    }

    // padding is done here
    for (i = 1; i <= padding; i++)
    {
        res_str[k++ ] = '=';
    }

    res_str[k] = '\0';

    return res_str;

}

// Driver code
int main()
{
    char input_str[] = "MENON";
    int len_str;

    // calculates length of string
    len_str = sizeof(input_str) / sizeof(input_str[0]);

    // to exclude '\0' character
    len_str -= 1;

    cout <<"Input string is : "<< input_str << endl;
    cout <<"Encoded string is : "<< base64Encoder(input_str, len_str)<< endl;
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to encode an ASCII
// string in Base64 format
#include <stdio.h>
#include <stdlib.h>
#define SIZE 1000

// Takes string to be encoded as input
// and its length and returns encoded string
char* base64Encoder(char input_str[], int len_str)
{
    // Character set of base64 encoding scheme
    char char_set[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";

    // Resultant string
    char *res_str = (char *) malloc(SIZE * sizeof(char));

    int index, no_of_bits = 0, padding = 0, val = 0, count = 0, temp;
    int i, j, k = 0;

    // Loop takes 3 characters at a time from
    // input_str and stores it in val
    for (i = 0; i < len_str; i += 3)
        {
            val = 0, count = 0, no_of_bits = 0;

            for (j = i; j < len_str && j <= i + 2; j++)
            {
                // binary data of input_str is stored in val
                val = val << 8;

                // (A + 0 = A) stores character in val
                val = val | input_str[j];

                // calculates how many time loop
                // ran if "MEN" -> 3 otherwise "ON" -> 2
                count++ ;

            }

            no_of_bits = count * 8;

            // calculates how many "=" to append after res_str.
            padding = no_of_bits % 3;

            // extracts all bits from val (6 at a time)
            // and find the value of each block
            while (no_of_bits != 0)
            {
                // retrieve the value of each block
                if (no_of_bits >= 6)
                {
                    temp = no_of_bits - 6;

                    // binary of 63 is (111111) f
                    index = (val >> temp) & 63;
                    no_of_bits -= 6;        
                }
                else
                {
                    temp = 6 - no_of_bits;

                    // append zeros to right if bits are less than 6
                    index = (val << temp) & 63;
                    no_of_bits = 0;
                }
                res_str[k++ ] = char_set[index];
            }
    }

    // padding is done here
    for (i = 1; i <= padding; i++)
    {
        res_str[k++ ] = '=';
    }

    res_str[k] = '\0;';

    return res_str;

}

// Driver code
int main()
{
    char input_str[] = "MENON";
    int len_str;

    // calculates length of string
    len_str = sizeof(input_str) / sizeof(input_str[0]);

    // to exclude '\0' character
    len_str -= 1;

    printf("Input string is : %s\n", input_str);
    printf("Encoded string is : %s\n", base64Encoder(input_str, len_str));
    return 0;
}
```

**Output**

```cpp
Input string is : MENON
Encoded string is : TUVOT04=

```

**时间复杂度:** O(2 * N)将位插入 val +从 val 中检索位
**练习:**实现一个 64 位的解码器
本文由[**<u>Arshpreet Soodan</u>**](https://github.com/soodan)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。