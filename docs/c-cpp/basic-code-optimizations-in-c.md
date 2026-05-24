# C 语言中的基本代码优化

> 原文:[https://www . geesforgeks . org/basic-code-optimization-in-c/](https://www.geeksforgeeks.org/basic-code-optimizations-in-c/)

通常，资源在不同的进程之间共享。假设你的程序占用了更多的资源，那么肯定会影响到其他需要同样资源的进程的性能。因此，我们需要编写和优化我们的程序，牢记资源，例如处理器的时间和主内存。
**以下是一些优化技巧**

1.  **<u>Optimizations in loop</u>**
    *   **Unroll small loops**: Most of the times Compiler does this automatically, but it is a good habit of writing optimized codes. Matrix updations using this is very advantageous.

        **程序 1:**

        ```cpp
        #include <stdio.h>
        int main(void)
        {
            int fact[5];
            fact[0] = 1;

            // Overhead of managing a counter
            // just for 4 iterations
            // is not a good idea
            for (int i = 1; i < 5; ++ i) {
                fact[i] = fact[i - 1] * i;
            }
            return 0;
        }
        ```

        **程序 2:**

        ```cpp
        #include <stdio.h>
        int main(void)
        {
            int fact[5] = { 1, 1, 2, 6, 24 };

            // Here the same work is done
            // without counter overhead
            return 0;
        }
        ```

    *   **避免循环计算**:我们应该避免任何数值或多或少恒定的计算。内部循环应该有最少可能的计算。
        T3】节目 1:

    ```cpp
    #include <stdio.h>
    int main(void)
    {
        int arr[1000];
        int a = 1, b = 5, c = 25, d = 7;

        // Calculating a constant expression
        // for each iteration is not good.
        for (int i = 0; i < 1000; ++ i) {
            arr[i] = (((c % d) * a / b) % d) * i;
        }
        return 0;
    }
    ```

    **程序 2:**

    ```cpp
    #include <stdio.h>

    int main(void)
    {
        int arr[1000];
        int a = 1, b = 5, c = 25, d = 7;

        // pre calculating the constant expression
        int temp = (((c % d) * a / b) % d);

        for (int i = 0; i < 1000; ++ i) {
            arr[i] = temp * i;
        }
        return 0;
    }
    ```

2.  **Avoid pointer Dereference in loop**: Pointer dereferencing creates lots of trouble in memory. So better assign it to some temporary variable and then use that temporary variable in the loop.
    **Program 1:**

    ```cpp
    #include <stdio.h>
    int main(void)
    {
        int a = 0;
        int* iptr = &a;

        // Dereferencing pointer inside loop
        // is costly
        for (int i = 1; i < 11; ++ i) {
            *iptr = *iptr + i;
        }
        printf("Value of a : %d", a);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Value of a : 55

    ```

    **程序 2:**

    ```cpp
    #include <stdio.h>
    int main(void)
    {
        int a = 0;
        int* iptr = &a;

        // Dereferencing pointer outside loop
        // and saving its value in a temp variable
        int temp = *iptr;

        for (int i = 1; i < 11; ++ i) {

            // performing calculations on temp variable
            temp = temp + i;
        }

        // Updating pointer using final value of temp
        *iptr = temp;

        printf("Value of a : %d", a);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Value of a : 55

    ```

3.  **使用寄存器变量作为内部循环的计数器**:存储在寄存器中的变量可以比存储在内存中的变量更快地被访问。
    **程序:**

    ```cpp
    #include <stdio.h>
    int main(void)
    {
        register int i = 0;
        register int j = 0;
        int n = 5;

        // using register variables
        // as counters make the loop faster
        for (i = 0; i < n; ++ i) {
            for (j = 0; j <= i; ++ j) {
                printf("* ");
            }
            printf("\n");
        }
        return 0;
    }
    ```

    **输出:**

    ```cpp
    * 
    * * 
    * * * 
    * * * * 
    * * * * *

    ```

4.  **<u>【快速数学】</u>**
    *   **避免不必要的整数除法**:除法运算比较慢，要尽量减少除法运算。
        T3】节目:

```cpp
#include <stdio.h>
int main(void)
{
    int a = 100, b = 2, c = 5;
    // int d=a/b/c;    two division operators
    int d = a / (b * c); // single division operator
    return 0;
}
```

*   **乘除 2** :乘除用左移(< <)乘除用右移(> >)。位运算将比乘法和除法运算快得多。对于简单的操作，编译器可能会自动优化代码，但在复杂表达式的情况下，总是建议使用位操作。
    **例:**

    ```cpp
    Multiply by 6 : a= a<<1 + a<<2; 
    Multiply by 7 : a= a<<3 - a;
    Divide by 8 : a= a>>3; // division by power of 2

    ```

    *   **简化表达式**:有时候我们可以通过简化表达式来减少一些运算。
    **例:**

    ```cpp
     a*b + a*b*c + a*b*c*d ---> (a*b)*(1 + c*(1 + d)) 
     L.H.S can be Simplified to R.H.S
     L.H.S  : 6 multiplications and 2 additions
     R.H.S  : 3 multiplications and 2 additions

    ```

    *   **<u>Optimization with Switch Statement</u>**
    Compilers translate switch statements in different ways. If case labels are small contiguous integer values, then it creates a jump table. This is very fast and doesn’t depend on the number of case labels also. If case labels are longer and not contiguous then it creates comparison tree i.e. if…else statements. So, in this case, we should keep the most frequent label first and the least frequent label should be at last.

    有时，除了一两个语句之外，我们在所有情况下都会看到大量重复的代码

    **示例:**

    ```cpp
    switch(expression)
    {
    case a:
           ........
           ........
           break;
    case b:
           ........
           ........
           break;
    case c:
           common statements;
           different statements;
           common statements;
           break;
    case d:
           common statements;
           different statements;
           common statements;
           break;   '
    case e:
           common statements;
           different statements;
           common statements;
           break;
    case f:
           common statements;
           different statements;
           common statements;
           break;
    default:
           break;      
    }

    ```

    我们可以将所有案例放在一起，并且可以只编写一次通用语句，而使用另一个开关在相关案例中编写不同的语句。这里我们将把案例 c，d，e，f 放在一起，写出共同的语句，然后我们可以使用另一个开关，在案例 c，d，e，f 中写出不同的语句，然后在这个开关之后，我们可以再次写出共同的语句。

    ```cpp
    switch(expression)
    {
    case a:
           ........
           ........
           break;
    case b:
           ........
           ........
           break;
    case c: 
    case d: 
    case e:   
    case f:
           common statements;
           switch(expression);
           {
           case c:
                  different statements;
                  break;
           case d:
                  different statements;
                  break;
           case e:
                  different statements;
                  break;
           case f:
                  different statements;
                  break;
           }  /*End of switch*/
           common statements;
           break;     

    default:
           break;      
    }/*End of switch*/

    ```

    *   **<u>更喜欢 int 而不是 char 或 short</u>**
    我们应该总是更喜欢 int 而不是 char，因为 C 用一个整数执行 char 的所有操作。在所有操作中，如将字符传递给函数或算术运算，**第一个字符将被转换为整数，在编译操作后，它将再次被转换为字符**。对于单个字符，这可能不会影响效率，但是假设在一个循环中执行 100 次相同的操作，那么它会降低程序的效率。*   **<u>优先选择前递增/后递减优先选择后递增/后递减</u>**
    在预递增中，它首先递增值，并将该值复制到变量位置，但在后递增中，它首先将该值复制到临时变量，递增该值，然后将该值复制到变量位置。如果后增量在一个循环中是 1000 次，它将降低效率。*   **<u>表达评估顺序</u>**
    *   ```cpp
         A || B 

        ```

        这里首先对 A 进行评估，如果是真的，那么就不需要对表达式 b 进行评估。因此，我们更希望在 A 处有一个大多数情况下评估为真的表达式。

    *   ```cpp
         A && B 

        ```

        这里首先对 A 进行评估，如果是假的，那么就不需要对表达式 b 进行评估。所以我们更希望在 A 的地方有一个大多数时候评估为假的表达式。