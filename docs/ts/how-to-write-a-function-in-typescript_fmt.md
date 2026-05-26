# 如何在 Typescript 中编写函数？

> 原文: [https://www.geeksforgeeks.org/how-to-write-a-function-in-typescript/](https://www.geeksforgeeks.org/how-to-write-a-function-in-typescript/)

在 [TypeScript](https://www.geeksforgeeks.org/introduction-to-typescript/) 中编写函数类似于在 JavaScript 中编写函数，但是增加了参数和返回类型。请注意，任何 JavaScript 函数都是完全有效的 TypeScript 函数。但是，我们可以通过添加类型来做得更好。

**语法:** 我们来看一个基本的 TypeScript 函数语法(有两个参数)

```
function functionName(arg1: <arg1Type>, 
        arg2: <arg2Type>): <returnType> {
    // Function body...
}
```

以下是一些有助于更好理解的功能。

**示例 1:** 在这个示例中，我们正在编写一个函数来添加两个数字

```
// TypeScript Code
// Following function returns the addition
// of it's two parameters
function addTwo(a: number, b: number): number {
    return a + b;
}

console.log(addTwo(7, 8)); // logs 15
```

**输出:**

```
15
```

**例 2:** 将两个数字相加，返回等价的十六进制字符串。

```
// Following function adds it's two parameters then
// returns it as string form in base 16
function getHexAddition(a: number, b: number): string {
    return (a + b).toString(16);
}

console.log(getHexAddition(10, 16)); // logs '1a'
```

**输出:**

```
1a
```

**添加可选参数和默认参数:** 添加可选参数超级简单，只需在参数名的末尾添加 `?`。

**例 3:** 写一个函数，记录一个有名字的早安消息，如果名字没有传递，那么只记录早安。

```
// Following function returns good morning
// message based on value of name passed
function goodMorning(name?: string): string {

    // if name exits use it as suffix else ignore name
    const suffix = (name ? `, ${name}.` : '.');
    return 'Good Morning' + suffix;
}

// logs 'Good Morning.'
console.log(goodMorning());

// logs 'Good Morning, Sam.'
console.log(goodMorning('Sam'));
```

**输出:**

```
Good Morning.
Good Morning, Sam.
```

**示例 4:** 编写一个返回 `base^{power}` 的函数，如果没有提供 `power`，则假设它为 1。

```
function pow(base: number, power = 1): number {
   return Math.pow(base, power);
}

console.log(pow(7));    // logs 7
console.log(pow(7, 2)); // logs 49
```

**输出:**

```
7
49
```