# 密码学中的 RSA 算法

> 原文：[https://www.geeksforgeeks.org/rsa-algorithm-cryptography/](https://www.geeksforgeeks.org/rsa-algorithm-cryptography/)

## 简介

RSA 算法是非对称密码算法。非对称实际上意味着它使用两个不同的密钥，即**公钥**和**私钥**。顾名思义，公钥给每个人，私钥保密。

## 非对称加密示例

1.  客户端（例如浏览器）将其公钥发送给服务器并请求一些数据。
2.  服务器使用客户端的公钥加密数据，并发送加密的数据。
3.  客户端接收并解密这些数据。

由于这是不对称的，除了浏览器之外，没有其他人可以解密数据，即使第三方拥有浏览器的公钥。

## RSA 算法思想

RSA 的思想是基于很难分解一个大整数的事实。公钥由两个数字组成，其中一个数字是两个大素数的乘积。而私钥也是由同样的两个质数推导出来的。因此，如果有人能分解出这个大数字，私钥就被泄露了。因此，加密强度完全取决于密钥大小，如果我们将密钥大小增加一倍或三倍，加密强度将呈指数级增长。RSA 密钥的长度通常为 1024 或 2048 位，但专家认为，1024 位密钥在不久的将来可能会被破解。但到目前为止，这似乎是一个不可行的任务。

## 生成公钥

选择两个质数。假设 `P = 53`，`Q = 59`。现在公钥的第一部分：`n = P*Q = 3127`。我们还需要一个小指数来表示 `e`：但是 `e` 必须是：
*   整数。
*   不是 `n` 的因数。
*   `1 < e < φ(n)`（`φ(n)` 在下面讨论），现在让我们考虑它等于 `3`。

我们的公钥是由 `n` 和 `e` 组成的。

## 生成私钥

我们需要计算 `φ(n)`：这样 `φ(n) = (P-1)(Q-1)`。所以，`φ(n) = 3016`。

现在计算私钥 `d`：`d = (k * φ(n) + 1) / e` 对于某个整数 `k`。对于 `k = 2`，`d` 的值是 `2011`。

现在我们已经准备好了——公钥 (`n = 3127`, `e = 3`) 和私钥 (`d = 2011`)。

## 加密与解密示例

现在我们将加密 `"HI"`：

将字母转换成数字：`H = 8`，`I = 9`。因此加密数据 `c = 89^e mod n`。因此我们的加密数据是 `1394`。

现在我们将解密 `1394`：解密数据 `= c^d mod n`。因此，我们的加密数据显示为 `89`，即 `H = 8`，`I = 9`，也就是 `"HI"`。

## C 语言实现

下面是小值 RSA 算法的 C 实现：

```c
// C program for RSA asymmetric cryptographic
// algorithm. For demonstration values are
// relatively small compared to practical
// application
#include<stdio.h>
#include<math.h>

// Returns gcd of a and b
int gcd(int a, int h)
{
    int temp;
    while (1)
    {
        temp = a%h;
        if (temp == 0)
          return h;
        a = h;
        h = temp;
    }
}

// Code to demonstrate RSA algorithm
int main()
{
    // Two random prime numbers
    double p = 3;
    double q = 7;

// First part of public key:
    double n = p*q;

// Finding other part of public key.
    // e stands for encrypt
    double e = 2;
    double phi = (p-1)*(q-1);
    while (e < phi)
    {
        // e must be co-prime to phi and
        // smaller than phi.
        if (gcd(e, phi)==1)
            break;
        else
            e++;
    }

// Private key (d stands for decrypt)
    // choosing d such that it satisfies
    // d*e = 1 + k * totient
    int k = 2;  // A constant value
    double d = (1 + (k*phi))/e;

// Message to be encrypted
    double msg = 20;

printf("Message data = %lf", msg);

// Encryption c = (msg ^ e) % n
    double c = pow(msg, e);
    c = fmod(c, n);
    printf("\nEncrypted data = %lf", c);

// Decryption m = (c ^ d) % n
    double m = pow(c, d);
    m = fmod(m, n);
    printf("\nOriginal Message Sent = %lf", m);

return 0;
}
// This code is contributed by Akash Sharan.
```

输出：

```
Message data = 12.000000
Encrypted data = 3.000000
Original Message Sent = 12.000000
```

本文由 **Mohit Gupta_OMG** 供稿🙂。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。