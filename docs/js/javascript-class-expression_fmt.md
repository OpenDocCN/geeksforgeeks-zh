# JavaScript 类表达式

> 原文: [https://www.geeksforgeeks.org/javascript-class-expression/](https://www.geeksforgeeks.org/javascript-class-expression/)

JavaScript 类是用 `class` 关键字声明的一类函数，用于实现面向对象范式。构造函数用于初始化类的属性。在 JavaScript 中创建[类](https://www.geeksforgeeks.org/es6-classes/)有两种方法。

*   类申报
*   类表达式

在本文中，我们将讨论用 JavaScript 声明类的类表达式以及如何使用它们。

## 类表达式

类表达式是 JavaScript 中创建类的另一种方式，它们可以是命名的，也可以是未命名的。如果命名，类名在内部使用，但不在类外部使用。

### 语法

*   使用命名类表达式:

```javascript
const variable_name = new Class_name {
    // class body
}
```

*   使用未命名的类表达式:

```javascript
const variable_name = class{
     //class body
}
```

### 示例 1：命名类表达式

```javascript
const Website = class Geek {
  constructor(name){
      this.name = name;
  }
  websiteName() {
    return this.name;
  }
};

const x = new Website("GeeksforGeeks");
console.log(x.websiteName());
```

**输出:**

```
GeeksforGeeks
```

### 示例 2：未命名类表达式

```javascript
const Website = class {
  constructor(name) {
    this.name = name;
  }
  returnName() {
    return this.name;
  }
};

console.log(new Website("GeeksforGeeks").returnName());
```

**输出:**

```
GeeksforGeeks
```

### 支持的浏览器

*   `Chrome` 42 及以上
*   `Edge` 13 及以上
*   `Firefox` 45 及以上版本
*   `Opera` 29 及以上
*   `Safari` 7 及以上版本