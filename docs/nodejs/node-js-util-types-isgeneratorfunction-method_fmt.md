# Node.js util.types.isGeneratorFunction()方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isgeneratorfunction-method/](https://www.geeksforgeeks.org/node-js-util-types-isgeneratorfunction-method/)

`util.types.isGeneratorFunction()`方法是`util`模块的内置API，主要是为了支持Node.js自身内部API的需求而设计的。
使用`util.types.isGeneratorFunction()`方法检查给定值是否是一个生成器函数。

## 语法

```js
util.types.isGeneratorFunction( value )
```

## 参数

该函数接受一个参数，如下所述：

*   `value`：这是将为生成器函数检查的值。

## 返回值

如果传递的值是生成器函数，则返回布尔值，即`true`，否则返回`false`。

下面的程序说明了Node.js中的`util.types.isGeneratorFunction()`方法：

## 示例

### 例 1

```js
// Node.js program to demonstrate the
// util.types.isGeneratorFunction() method

// Import the util module
const util = require('util');

// Getting the generator function
let GeneratorFunction = 
      Object.getPrototypeOf(function*(){}).constructor

// Checking the generator function
let genFn = new GeneratorFunction();
console.log(genFn);

isGenFn = util.types.isGeneratorFunction(genFn);
console.log("Object is a generator function:", isGenFn);

// Checking a normal function
let normalFn = function helloWorld() {};
console.log(normalFn);

isGenFn = util.types.isGeneratorFunction(normalFn);
console.log("Object is a generator function:", isGenFn);
```

**输出：**

```js
[GeneratorFunction: anonymous]
Object is a generator function: true
[Function: helloWorld]
Object is a generator function: false
```

### 例 2

```js
// Node.js program to demonstrate the
// util.types.isGeneratorFunction() method

// Import the util module
const util = require('util');

// Checking a generator function
let genFn = function* getID() {
      let id = 0;
      while (true)
        yield id++;
};
console.log(genFn);

isGenFn = util.types.isGeneratorFunction(genFn);
console.log("Object is a generator function:", isGenFn);

// Checking a normal function
let normalFn = function helloGeeks() { 
      console.log("Hello World")
};

console.log(normalFn);

isGenFn = util.types.isGeneratorFunction(normalFn);
console.log("Object is a generator function:", isGenFn);
```

**输出：**

```js
[GeneratorFunction: getID]
Object is a generator function: true
[Function: helloGeeks]
Object is a generator function: false
```

**参考：** [https://nodejs.org/api/util.html#util_util_types_isgeneratorfunction_value](https://nodejs.org/api/util.html#util_util_types_isgeneratorfunction_value)