# 偶数和奇数自然数的立方之和

> 原文：[https://www.geeksforgeeks.org/sum-cubes-even-odd-natural-numbers/](https://www.geeksforgeeks.org/sum-cubes-even-odd-natural-numbers/)

我们知道[前 n 个自然数](https://www.geeksforgeeks.org/program-cube-sum-first-n-natural-numbers/)的立方之和为 `= (n(n+1)/2)^2`。

## 前 n 个偶数自然数的立方之和

`2^3+4^3+6^3+……+(2n)^3`

```
Even Sum = 2^3 + 4^3 + 6^3 + .... + (2n)^3
        if we multiply by 2^3 then 
        = 2^3 x (1^3 + 2^3 + 3^3 + .... + (n)^3)
        = 2^3 + 4^3 + 6^3 + ......... + (2n)^3
        =  2^3 (n(n+1)/2)^2
        =  8(n(n+1))^2/4
        =  2(n(n+1))^2
```

**示例：**

```
Sum of cube of first 4 even numbers = 2^3 + 4^3 + 6^3 + 8^3 
 put n = 4     = 2(n(n+1))^2
               = 2*(4*(4+1))^2
               = 2(4*5)^2
               = 2(20)^2
               = 800
 8 + 64 + 256 + 512 = 800
```

[前 n 个偶数立方之和程序](https://www.geeksforgeeks.org/sum-of-cubes-of-first-n-even-numbers/)

## 前 n 个奇数自然数的立方之和

我们需要计算 `1^3+3^3+5^3+…+ (2n-1)^3`

```
OddSum   = (Sum of cubes of all 2n numbers) - (Sum of cubes of first n even numbers)
         =  (2n(2n+1)/2)^2 - 2(n(n+1))^2 
         =  n^2(2n+1)^2 - 2* n^2(n+1)^2
         =  n^2[(2n+1)^2 - 2*(n+1)^2]
         =  n^2[4n^2 + 1 + 4n - 2n^2 - 2 - 4n]
         =  n^2(2n^2 - 1)
```

**示例：**

```
Sum of cube of first 4 odd numbers = 1^3 + 3^3 + 5^3 + 7^3 
 put n = 4     = n^2(2n^2 - 1)
               = 4^2(2*(4)^2 - 1)
               = 16(32-1)
               =  496
 1 + 27 + 125 + 343 = 496
```

[前 n 个奇数立方之和程序](https://www.geeksforgeeks.org/sum-of-cubes-of-first-n-odd-natural-numbers/)