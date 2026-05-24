# 逻辑运算符的操作数顺序

> 原文:[https://www.geeksforgeeks.org/g-fact-74/](https://www.geeksforgeeks.org/g-fact-74/)

逻辑运算符&&，||的操作数顺序在 C/C++ 中很重要。

在数学中，逻辑“与”、“或”等运算是可交换的。即使我们交换运营商的 RHS 和 LHS，结果也不会改变。

在 C/C++ 中(也可能在其他语言中)，即使这些运算符是可交换的，它们的顺序也很关键。例如见下面的代码，

```cpp
// Traverse every alternative node
while( pTemp && pTemp->Next )
{
   // Jump over to next node
   pTemp = pTemp->Next->Next;
}
```

第一部分 *pTemp* 将针对空值进行评估，然后是 *pTemp- >下一步*。如果先放置 *pTemp- >下一个*，指针 *pTemp* 将被取消引用，当 *pTemp* 为空时会出现运行时错误。

必须遵守命令。事实上，它有助于生成高效的代码。当指针 *pTemp* 为空时，由于 AND ( & &)表达式的结果保证为 0，第二部分将不被求值。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。