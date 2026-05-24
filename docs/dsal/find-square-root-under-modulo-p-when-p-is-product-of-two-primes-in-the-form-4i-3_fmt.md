# 求模 p 下的平方根（当 p 是 4i+3 形式的两个素数的乘积时）

> 原文：[https://www.geeksforgeeks.org/find-square-root-under-modulo-p-when-p-is-product-of-two-primes-in-the-form-4i-3/](https://www.geeksforgeeks.org/find-square-root-under-modulo-p-when-p-is-product-of-two-primes-in-the-form-4i-3/)

给定一个整数`N`和一个整数`P`表示两个素数的乘积，任务是在模`P`下找到所有可能的`N`的平方根，如果它存在的话。给出了`P`是`p1`和`p2`的乘积，其中`p1`和`p2`是形式为`4i + 3`的素数，其中`i`为任意整数。这样的素数的一些例子是(7，11，19，23，31)。

**例：**

> **输入：** `N = 67`，`P = 77`
> **输出：** `23 65 12 54`
> **解释：**
> 所有可能的答案为(23，65，12，54)
> **输入：** `N = 188`，`P = 437`
> **输出：** `25 44 393 412`
> **解释：**
> 所有可能的答案都是(25，44，393，412)

### 天真法
解决这个问题最简单的方法是考虑从`2`到`P–1`的所有数字，对于每个数字，在模`P`下检查是否是`N`的平方根。如果发现是真的，那么打印这个数字并中断。
**时间复杂度：** `O(P)`
**辅助空间：** `O(1)`

### 高效途径
对上述途径进行优化，思路是利用素因式分解得到两个因子`p1`和`p2`，然后利用 mod P 下的平方根求出两者的平方根，然后用中国剩余定理求平方根模 `p1 * p2`。每组将包含两个方程(因为模`p1`和`p2`各有两个平方根)。将它们结合起来，得到了四组方程，给出了四种可能的答案。

按照以下步骤解决此问题：

*   使用质因数分解对数字`P`进行因数分解。因素将是两个质数`p1`和`p2`。
*   求平方根模素数`p1`和`p2`。
*   找到两组答案，每个质数一组。每组包含两个数字。
*   因此，如果从每组中选择一个数字，将有 4 组方程。
*   执行中国剩余定理找到平方根模 `p1 * p2` 并打印出来。

下面是上述方法的实现，其中 Java 中的大整数类用于处理非常大的数字：

### Java 实现

```java
// Java program for the above approach
import java.math.*;
import java.util.*;

class SqrtMod {

// Function to find the modulo inverse
    // of a with respect to m
    static BigInteger modInverse(BigInteger a,
                                 BigInteger m)
    {

        BigInteger m0 = m;
        BigInteger y = new BigInteger("0"),
                   x = new BigInteger("1");

        if (m.compareTo(new BigInteger("1")) == 0)
            return new BigInteger("0");

        // Perform Extended Euclid Algorithm
        while (a.compareTo(new BigInteger("1")) > 0) {

            if (m.toString().equals("0"))
                break;
            BigInteger q = a.divide(m);

            BigInteger t = m;

            // M is remainder now, process
            // Extended Euclid Algorithm
            m = a.mod(m);
            a = t;

            t = y;
            y = x.subtract(q.multiply(y));
            x = t;
        }

        // Make x positive
        while (x.compareTo(new BigInteger("0")) < 0)
            x = x.add(m0);
        return x;
    }

    // Function to apply the Chinese
    // Remainder Theorem
    static String CRT(BigInteger num[],
                      BigInteger rem[],
                      int k)
    {

        BigInteger prod = new BigInteger("1");

        // Find product of all numbers
        for (int i = 0; i < k; i++)
            prod = prod.multiply(num[i]);

        BigInteger result = new BigInteger("0");

        // Apply the above formula
        for (int i = 0; i < k; i++) {
            BigInteger pp = prod.divide(num[i]);
            result = result.add(rem[i]
                                    .multiply(modInverse(pp,
                                                         num[i]))
                                    .multiply(pp));
        }

        // Return result
        return result.mod(prod).toString();
    }

    // Function to perform modular
    // exponentiation
    static BigInteger powMod(BigInteger base1,
                             BigInteger exponent,
                             BigInteger modulus)
    {

        BigInteger result = new BigInteger("1");

        base1 = base1.mod(modulus);

        while (exponent
                   .compareTo(new BigInteger("0"))
               > 0) {

            if (exponent
                    .mod(new BigInteger("2"))
                    .equals(new BigInteger("1")))

                result = (result.multiply(base1))
                             .mod(modulus);

            exponent = exponent
                           .divide(new BigInteger("2"));
```

# 模平方根算法实现

## 模幂运算
```java
base1 = base1
        .multiply(base1)
        .mod(modulus);
}
// Return the result
return result;
}
```

## 模平方根计算
```java
// Function that returns square root
// of n under modulo p if exists
static BigInteger squareRoot(
    BigInteger n,
    BigInteger p)
{
```

### 无效输入处理
```java
// For Invalid Input
if (!p.mod(new BigInteger("4"))
         .equals(new BigInteger("3"))) {

    System.out.print("Invalid Input");
    return new BigInteger("-1");
}

n = n.mod(p);
```

### 计算候选解
```java
// Try "+(n^((p + 1)/4))"
BigInteger x = powMod(n,
                      (p.add(new BigInteger("1")))
                        .divide(new BigInteger("4")),
                      p);

if ((x.multiply(x)).mod(p).equals(n)) {
    return x;
}

// Try "-(n ^ ((p + 1)/4))"
x = p.subtract(x);
if ((x.multiply(x)).mod(p).equals(n)) {
    return x;
}
```

### 无解情况
```java
// If none of above two work,
// then sqrt doesn't exist
return new BigInteger("-1");
}
```

## 计算平方根的上取整
```java
// Function to find the ceiling
// of square root of a number
public static BigInteger
sqrtC(BigInteger x)
{
```

### 边界条件处理
```java
// If number < zero
if (x.compareTo(BigInteger.ZERO) < 0) {
    return new BigInteger("-1");
}

// If number is zero or 1
if (x == BigInteger.ZERO
    || x == BigInteger.ONE) {
    return x;
}
```

### 迭代计算
```java
BigInteger two
    = BigInteger.valueOf(2L);

BigInteger y;

// Iterate to find the square root
for (y = x.divide(two);
     y.compareTo(x.divide(y)) > 0;
     y = ((x.divide(y)).add(y)).divide(two))
    ;
if (x.compareTo(y.multiply(y)) == 0) {
    return y;
}
else {
    return y.add(BigInteger.ONE);
}
}
```

## 数字因式分解
```java
// Function to factorise number P
static BigInteger[] factorise(BigInteger p)
{
```

### 初始化变量
```java
BigInteger ans[] = new BigInteger[2];
BigInteger b = new BigInteger("2");

BigInteger ONE = new BigInteger("1");
BigInteger ZERO = new BigInteger("0");
```

### 迭代查找因子
```java
// Iterate over [2, sqrt(N)]
for (; b.compareTo(
           sqrtC(p).add(ONE))
       < 0;
     b = b.add(ONE)) {

    // Check if mod is zero
    if (p.mod(b).equals(ZERO)) {
        ans[0] = b;
        ans[1] = p.divide(b);
    }
}

// Return the ans
return ans;
}
```

## 求解模平方根
```java
// Function to find the all possible
// squareRoot of a under modulo m
public static void
solve(BigInteger a, BigInteger m)
{
```

### 分解模数
```java
// Find factorization of m
BigInteger s[] = factorise(m);
BigInteger ZERO = new BigInteger("0");

// If number P is not product
// of two primes
if (!s[0].multiply(s[1]).equals(m)) {

    System.out.println("Not a product "
                       + "of two primes");
}
```

### 计算平方根
```java
// Find the numbers
else {

    BigInteger s1[] = new BigInteger[4];
    BigInteger a1[] = new BigInteger[4];
    BigInteger a2[] = new BigInteger[2];

    // Find squareRoot
    a1[0] = squareRoot(a.mod(s[0]), s[0]);
    a1[1] = squareRoot(a.mod(s[1]), s[1]);

    a1[2] = a1[0].multiply(new BigInteger("-1"));
    a1[3] = a1[1].multiply(new BigInteger("-1"));
```

### 调整负值
```java
// Compare to Zero
while (a1[2].compareTo(ZERO) < 0)
    a1[2] = a1[2].add(s[0]);
while (a1[3].compareTo(ZERO) < 0)
    a1[3] = a1[3].add(s[1]);
s1[0] = s[0];
s1[1] = s[1];
s1[2] = s[0];
s1[3] = s[1];
```

### 检查解的存在性
```java
// Condition for no solution
if (a1[0].equals(new BigInteger("-1"))
    || a1[1].equals(new BigInteger("-1"))) {

    System.out.println("No Solution");
}
```

### 使用中国剩余定理求解
```java
// Else print all possible answers
else {

    // Perform Chinese Remainder
    // Theorem and print numbers
    System.out.print(
        CRT(s, a1, 2) + " ");

    a2[0] = a1[0];
    a2[1] = a1[3];

    System.out.print(
        CRT(s, a2, 2) + " ");

    a2[0] = a1[2];
    a2[1] = a1[1];

    System.out.print(
        CRT(s, a2, 2) + " ");

    a2[0] = a1[2];
    a2[1] = a1[3];

    System.out.print(
        CRT(s, a2, 2) + " ");
}
}
}
```

## 主函数
```java
// Driver Code
public static void
    main(String[] args) throws Exception
{

// Given Number N
BigInteger N = new BigInteger("188");

// Given product of Prime Number
BigInteger P = new BigInteger("437");

// Function Call
solve(N, P);
}
}
```

**输出:**
```
25 44 393 412
```

**时间复杂度:** `O(√P + logN)`
**辅助空间:** `O(1)`