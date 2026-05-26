# 打字稿中的数据类型

> 原文:[https://www.geeksforgeeks.org/data-types-in-typescript/](https://www.geeksforgeeks.org/data-types-in-typescript/)

无论何时创建一个变量，目的都是为该变量赋值，但是可以为该变量赋值的类型取决于该变量的数据类型。在类型脚本中，类型系统表示类型脚本支持的不同类型的数据类型。数据类型分类如下:

## 内置数据类型

类型脚本有一些预定义的数据类型:

| 内置数据类型 | 关键字 | 描述 |
| --- | --- | --- |
| 数字 | `number` | 它用于表示整数和浮点数 |
| 布尔代数学体系的 | `boolean` | 代表真与假 |
| 线 | `string` | 它用于表示一系列字符 |
| 空的 | `void` | 通常用于函数返回类型 |
| 空 | `null` | 当对象没有任何值时使用它 |
| 不明确的 | `undefined` | 降级给未初始化变量的值 |
| 任何的 | `any` | 如果变量被声明为任何数据类型，那么任何类型的值都可以分配给该变量 |

示例:

> `let a: number = 0;`
>
> `let b: number = 123;`
>
> `let c: number = 123.456;`
>
> `let d: string = 'Geeks';`
>
> `let e: undefined = undefined;`
>
> `let f: boolean = true;`
>
> `let g: number = 0b111001;` //二进制
>
> `let h: number = 0o436;` //八进制
>
> `let i: number = 0xADF0d;` //十六进制

## 用户自定义数据类型

除了内置的数据类型，用户还可以定义自己的数据类型。用户定义的类型包括枚举(`enum`)、类、接口、数组和元组。

**注:**在内置数据类型中，`any`都是一种特殊的数据类型，也是所有数据类型的超级数据类型。如果一个变量用任何数据类型声明，那么我们可以给这个变量赋值。

**示例:**

> `let a: any = null;`
>
> `let b: any = 123;`
>
> `let c: any = 123.456;`
>
> `let d: any = 'Geeks';`
>
> `let e: any = undefined;`
>
> `let f: any = true;`