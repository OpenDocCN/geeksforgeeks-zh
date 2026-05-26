# 如何在 TypeScript 中检查接口类型？

> 原文: [https://www.geeksforgeeks.org/how-to-check-interface-type-in-typescript/](https://www.geeksforgeeks.org/how-to-check-interface-type-in-typescript/)

Typescript 是一种纯面向对象的编程语言，由类、接口、继承等组成。它很严格，像 Java 一样静态类型化。接口用于在 typescript 中定义联系人。一般来说，它定义了实体的规范。下面是一个汽车接口或合同的例子。

```
interface Audi {
    length: number;
    width: number;
    wheelbase: number;
    price:number;
    numberOfAirBags:number;
    seatingCapacity: number;
    getTyrePressure: () => number;
}
```

## 方法:

*   声明一个接口为字符串，包含名称和类型。
*   现在创建一个自定义函数来检查接口类型。
*   如果传递的参数中存在 `name` 属性，该函数返回一个布尔值。
*   现在使用 `if` 语句检查函数返回的值，你可以根据需求执行进一步的操作。

## 例 1:

```
interface Student{
    name:string;
}

var geek:any = { 
    name: "Jairam" 
    };

function instanceOfStudent(data: any): data is Student {
    return 'name' in data;
}

if (instanceOfStudent(geek)) {
    document.write("Student Name is "+ geek.name);
}
```