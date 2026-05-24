# 布尔代数中德摩根定律的证明

> 原文：[https://www.geeksforgeeks.org/proof-of-de-morgans-laws-in-boolean-algebra/](https://www.geeksforgeeks.org/proof-of-de-morgans-laws-in-boolean-algebra/)

**语句：**
**1. `(x+y)'= x'. y'`**
**2. `(x.y)'=x'+y'`**

**证明：**
这里可以看出，我们需要证明两个命题是相辅相成的。
我们知道 `A+A'=1` 和 `A.A'=0`，这是`湮灭定律`。因此，如果我们证明上述法律陈述的这些条件，那么我们将证明它们是相互补充的。

### 对于陈述 1：
我们需要证明：
```
(x+y)+x'.y'=1
```
和
```
(x'.y').(x+y)=0
```

#### 案例 1。
```
(x+y)+x'.y'=1
```
```
LHS: (x+y)+x'.y' =(x+y).(x+x')+x'.y'
=x.x+x.y+y.x'+x'.y'=x+x.y+y.x'+x'.y'  (利用分配属性)
=x+x.y+x'.(y+y')
=x+x.y+x'=x+x'+x.y
=1+x.y=1=RHS
```
遂被证明。

#### 案例二。
```
(x'.y').(x+y)=0
```
```
LHS: (x'.y').(x+y)=x.(x'y')+y.(x'.y')
=x.0+0.x'=0=RHS
```
遂证。

### 对于陈述 2：
我们需要证明：
```
x.y+(x'+y')=1
```
和
```
x.y.(x'+y')=0
```

#### 案例 1。
```
x.y+(x'+y')=1
```
```
LHS: x.y+(x'+y')=(x+x'+y').(y+x'+y')
(我们知道 A+BC=(A+B).(A+C))
=(1+y').(1+x')=1=RHS
```
遂证。

#### 案例二。
```
x.y.(x'+y')=0
```
```
LHS: (x.y).(x'+y')=x.x'.y+x.y.y'
=0=RHS
```
遂证成。

利用布尔代数的恒等式证明了德摩根定理。