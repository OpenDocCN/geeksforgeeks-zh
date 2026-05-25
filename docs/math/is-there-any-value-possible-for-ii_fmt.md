# i^i 有没有可能的价值

## 原文
[https://www.geeksforgeeks.org/is-there-any-value-possible-for-ii/](https://www.geeksforgeeks.org/is-there-any-value-possible-for-ii/)

众所周知[复数](https://www.geeksforgeeks.org/complex-numbers-c-set-1/)这个话题，我们很熟悉 iota (`i`)这个术语，其中 `i = √(-1)`。一个问题出现了，`i^i`有没有任何可能的价值。
所以，它简单的回答是肯定的，有一个值为 `i^i`。下面为其提及解决方案。
我们要找到 `i^i` 的值。所以，让 `y = i^i`
两边取 ln，

```
ln(y)= i ln(i) ----- ( i )      [ ln (ab) = b*ln(a) ]
```

现在，为了求解 `ln(i)`，我们必须理解以下概念:
在复数的极坐标表示中，我们写 `z = re^{iθ}`，其中–

```
z = a + ib,
r = |a2 + b2|
θ = tan-1(b/a),
So, taking log on both sides of the equation z = reiθ  
ln(z) = ln(r) + iθ             [ln(ea) = a, and ln(a*b) = ln(a) + ln(b)]
Putting the value of z, r and θ in the above equation
ln(a+ib) = ln(|a2 + b2|) + i*tan-1(b/a)
```

所以，写出 `ln(i) = ln(0 + 1i)`，并应用上面的公式

```
ln(0+1i) = ln(|02 + 12|) + i*tan-1(1/0)
ln(i) = ln1 + i*∏/2     [ tan-1(1/0) = tan-1(∞) = ∏/2 ]
ln(i) = i*∏/2           [ ln1 = 0 ]
```

现在把 `ln(i)`的值放到等式(I)中

```
ln(y) = i * ( i*∏/2 )
ln(y) = i2 * ∏/2  
ln(y) = -1 * ∏/2    [i2 = -1]
ln(y) = -∏/2   
y = e -∏/2           [ln(a) = b ⇒ a = eb]
```

正如我们假设的 `y = i^i`。
所以，

```
ii =  e -∏/2    
```

如果我们借助计算器计算 `e^{-∏/2}` 的值，我们得到它的近似值为 0.20788。

```
ii = 0.20788
```