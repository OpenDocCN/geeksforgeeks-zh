# 在 C# 中实现堆栈

> 原文:[https://www.geeksforgeeks.org/implementing-stack-c-sharp/](https://www.geeksforgeeks.org/implementing-stack-c-sharp/)

堆栈是一种线性数据结构。输入/输出遵循后进先出模式。在堆栈中执行以下三个基本操作:

*   **Push:** Add an item to the stack. If the stack is full, it is called a stack overflow condition.
*   **Eject:** Remove an item from the stack. These items pop up in the reverse order of push. If the stack is empty, it is called a stack underflow condition.
*   **peek:** Returns the top element of the stack.

下面给出了使用数组实现堆栈的 C# 代码

```cs
using System;

namespace StackImplementation
{
    internal class Stack
    {
        static readonly int MAX = 1000;
        int top;
        int[] stack = new int[MAX];

        bool IsEmpty()
        {
            return (top < 0);
        }
        public Stack()
        {
            top = -1;
        }
        internal bool Push(int data)
        {
            if (top >= MAX)
            {
                Console.WriteLine("Stack Overflow");
                return false;
            }
            else
            {
                stack[++top] = data;
                return true;
            }
        }

        internal int Pop()
        {
            if (top < 0)
            {
                Console.WriteLine("Stack Underflow");
                return 0;
            }
            else
            {
                int value = stack[top--];
                return value;
            }
        }

        internal void Peek()
        {
            if (top < 0)
            {
                Console.WriteLine("Stack Underflow");
                return;
            }
            else
                Console.WriteLine("The topmost element of Stack is : {0}", stack[top]);
        }

        internal void PrintStack()
        {
            if (top < 0)
            {
                Console.WriteLine("Stack Underflow");
                return;
            }
            else
            {
                Console.WriteLine("Items in the Stack are :");
                for (int i = top; i >= 0; i--)
                {
                    Console.WriteLine(stack[i]);
                }
            }
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Stack myStack = new Stack();

            myStack.Push(10);
            myStack.Push(20);
            myStack.Push(30);
            myStack.Push(40);
            myStack.PrintStack();
            myStack.Peek();
            Console.WriteLine("Item popped from Stack : {0}", myStack.Pop());
            myStack.PrintStack();
        }
    }
}
```

输出:

```cs
Items in the Stack are :
40
30
20
10
The topmost element of Stack is : 40
Item popped from Stack : 40
Items in the Stack are :
30
20
10

```

本文由 **Ankit Sharma** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。