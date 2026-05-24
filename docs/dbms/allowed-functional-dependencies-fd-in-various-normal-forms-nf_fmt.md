# 各种正常形式的允许功能依赖关系

> 原文：[https://www.geeksforgeeks.org/allowed-functional-dependencies-fd-in-various-normal-forms-nf/](https://www.geeksforgeeks.org/allowed-functional-dependencies-fd-in-various-normal-forms-nf/)

先决条件 – [功能依赖和属性闭包](https://www.geeksforgeeks.org/functional-dependency-and-attribute-closure/)

我们都知道以下几点：

*   2NF 不允许部分依赖。
*   3NF 不允许传递依赖。
*   BCNF 不允许任何非超键的属性成为决定因素。

让我们检查所有可能的函数依赖关系，找出什么是允许的，什么是不允许的。请注意：`prime` 属性是任何候选关键字的一部分。`non prime` 属性是不属于任何候选关键字的属性。因此，建议您从给定的函数依赖项中找出所有可能的候选键，并标记质数和非质数属性。

## 1. 第二范式 (2NF)

### 不允许的 FDs

```
prime -> non prime
```

如果说你的函数依赖是 `A->X` 的形式，其中 `A` 是一个质数属性而不是一个键，`X` 是非质数属性，那么这样的 FD 在 2NF 中是不允许的。

### 允许的 FDs

```
Prime -> Prime
Non prime -> Prime/Non prime
Key -> Prime/Non prime
Prime + Non prime combination -> Prime/Non Prime
```

*   如果 `A` 是一个质数属性（尽管不是键），它可以决定另一个质数属性。
*   如果 `A` 是一个非质数属性，它可以决定一个质数/非质数属性。
*   如果 `A` 是一个键，它可以决定一个质数/非质数属性。

## 2. 第三范式 (3NF)

### 不允许的 FDs

```
Prime -> Non prime  (2NF requirement)
Non prime -> Non prime  (3NF special)
```

### 允许的 FDs

```
Prime -> Prime
Non prime -> Prime
Key -> Prime/Non prime
Prime + Non Prime -> Prime/Non prime
```

## 3. 博伊斯-科德范式 (BCNF)

### 不允许的 FDs

```
Prime -> Non prime
Non prime -> Non prime
Prime -> Prime
Non prime -> Prime
```

### 允许的 FDs

```
Key -> Prime/Non prime
```