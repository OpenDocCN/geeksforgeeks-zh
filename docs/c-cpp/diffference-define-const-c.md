# C 中#define 和 const 的区别？

> 原文:[https://www.geeksforgeeks.org/diffference-define-const-c/](https://www.geeksforgeeks.org/diffference-define-const-c/)

**#定义**是[预处理器指令](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)。由#define [宏](https://gcc.gnu.org/onlinedocs/cpp/Macros.html#:~:text=A%20macro%20is%20a%20fragment,has%20been%20given%20a%20name.&text=Object-like%20macros%20resemble%20data,not%20know%20anything%20about%20keywords.)定义定义的数据是经过预处理的，因此您的整个代码都可以使用它。这可以释放空间并增加编译时间。

**const** 变量被认为是变量，而不是宏定义。

长话短说: **CONST** s 由编译器处理，其中 as **#DEFINE** s 由[预处理器](https://www.tutorialspoint.com/cprogramming/c_preprocessors.htm)处理。

const 相对于#define 的最大优势是类型检查。#定义不能进行类型检查，因此这可能会在尝试确定[数据类型](https://www.tutorialspoint.com/cprogramming/c_data_types.htm)时导致问题。相反，如果变量是常数，那么我们可以获取存储在该常数变量中的数据类型。

由于**常量被认为是变量**，我们可以在它们上面使用指针。这意味着我们可以对一个常规变量进行类型转换、移动地址和其他操作，除了改变数据本身，因为分配给该变量的数据是常量。

总的来说， **const 是更好的选择**如果我们有选择的话，它可以成功的应用到代码中。存在#define 不能被 const 替换的情况。例如，#define 可以取参数(参见[本](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)举例)。#define 还可以用来将程序中的某些文本替换为另一个文本。

本文由**阿沛·拉提**供稿，由 [**诺兰·塔夫特**](https://github.com/dev-nolant) 编辑。如果您发现任何不正确的地方，请写评论，或者您想分享更多关于上面讨论的主题的信息