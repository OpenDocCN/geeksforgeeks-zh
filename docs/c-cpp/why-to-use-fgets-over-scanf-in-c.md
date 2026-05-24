# 为什么在 C 语言中使用 fgets()而不是 scanf()？

> 原文:[https://www . geesforgeks . org/why-to-use-fgets-over-scanf-in-c/](https://www.geeksforgeeks.org/why-to-use-fgets-over-scanf-in-c/)

任何时候你使用一个 ***f** 函数，无论是 **printf** 、 **scanf** 还是它们的派生词(fprintf、fscanf 等等…)，你做的事情都比你可能意识到的要多。你不仅在读(或写)什么，而且——问题就在这里——你在 ***解读*** 它。格式字符串可以被认为是一种“评估”函数，就像你用 Lisp 编程一样。所以简单地读取用户输入并将其回显的**问题**是恶意的参与者可以简单地插入函数指针或可执行代码，瞧，你不再控制了。

**使用 scanf()的优势:**
用户**不需要知道栈的大小**，也就是起始代码是一百字节。这很好，尽管任何人都可以坐在那里尝试越来越长的输入字符串，直到出现 **[BufferOverflow](https://www.geeksforgeeks.org/buffer-overflow-attack-with-example/) 错误**。理想情况下，您只需编写一个脚本，自动尝试增加字符串大小并读取程序的退出代码。一旦它检测到一个错误，您只需返回堆栈的精确估计。任何使用内存地址随机化的现代操作系统都会使劫持应用程序的整个过程变得更加困难，但这绝不是不可能的。

**fgets() over scanf():**

[fgets](https://www.geeksforgeeks.org/fgets-gets-c-language/) 功能是**文件获取字符串**的缩写。请记住，文件在*nix 系统上几乎可以是任何东西(套接字、流或实际文件)，因此我们可以使用它来读取标准输入，同样，从技术上讲，它也是一个文件。这也使得我们的程序更加**健壮**，因为如源代码中所述，只需调整代码从命令行、文件或 stdin 读取，没有太多麻烦。

至关重要的是，fgets 函数还允许我们指定特定的**缓冲区长度**，从而禁止任何缓冲区溢出攻击。如果您查看下面的完整代码，您会注意到默认缓冲区大小被定义为一个宏。请记住，C 不能使用“const int”变量来正确初始化数组。您可以使用可变长度数组(VLA 的)破解它，但这并不理想，我强烈建议不要这样做。因此，虽然在 C++ 中，我们通常使用字面上的其他任何东西，但这里我们确实使用预处理器宏，但请记住，C 和 C++ 在静态类型检查方面有着截然不同的能力，即 C++ 优于 C。因此，fgets()方法实际上可以在输入/输出期间处理错误。

因此，实际读取用户输入的代码如下:

```cpp
char* inputBuffer = malloc(sizeof(char) * DEFAULT_BUFFER_SIZE);
memset(inputBuffer, NUL, DEFAULT_BUFFER_SIZE);

char* result = NULL;

while (result == NULL) {
    result = fgets(inputBuffer, DEFAULT_BUFFER_SIZE, stdin);

    if (inputBuffer[strlen(inputBuffer) - 1] != '\n') {
        ErrorInputStringTooLong();

        // Since 'result' is the canary
        // we are using to notify of a failure
        // in execution, set it to NULL, to indicate an error.
        // This is a useful value because
        // if for some reason the fgets f/nction were
        // to fail, the return value would also be NULL.

        result = NULL;
    }
}
```

正如预期的那样，我们动态分配一个预定大小的**缓冲区**。动态分配它，而不是堆栈分配它给我们另一层**保护**防止堆栈粉碎。

**注意:**我们在 inputBuffer 中显式清零内存。c 不会为你做任何事，malloc 也不例外。对 malloc 的调用返回一个指向所请求内存的第一个内存单元的指针，但是这些单元中的每一个单元的值都与调用之前的值相同。实际上，它们是垃圾，所以我们把它们剔除。还要注意，通过置零，我们自动给自己一个空终止符，尽管 fgets 函数确实在输入字符串的末尾附加了一个空值，前提是缓冲区中有足够的空间。

**用户输入过长字符串时:**

您会注意到，我检查以确保最后读取的值不是新行。如果这是真的，这意味着用户输入的输入字符串太长了。为了解决这个问题，我们需要将我们的“结果”变量设置为空，这样我们就可以再次循环这个循环，但是我们还需要清空输入缓冲区。否则，程序将只读取尚未使用的旧输入，而不是提示用户进行额外输入。为了处理这个问题，我提供了两个额外的函数。

```cpp
static inline void ErrorInputStringTooLong()
{

    // NOTE: Print to stderr, not to stdout.
    fprintf(stderr, "[ERROR]: The input was too long, please try again.\n");

    // Having notified the user,
    // clear the input buffer and return.
    ClearInputBuffer();
}

static inline void ClearInputBuffer()
{

    // This variable is merely here to munch the garbage out of the input
    // buffer. As long as the input buffer's current character is not either
    // a new line character or the end of input, keep reading characters. This
    // seems to be the only portable way of clearing the input buffer.
    char c = NUL;

    while ((c = getchar()) != '\n' && c != EOF) {
        // Do nothing until input buffer fully flushed.
    }
}
```

**注意:**通常，要清除输入缓冲区，只需调用 **fseek(stdin，0，SEEK _ END)；**但似乎并不是每个平台都适用。因此，使用上述方法。

**注意:**如果 fgets 返回**错误**，你应该打电话给 **ferror()** 来找出问题所在。