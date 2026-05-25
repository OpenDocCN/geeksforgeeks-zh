# 构造器: new vm.Script()方法

> 原文: [https://www.geeksforgeeks.org/node-js-constructor-new-vm-script-method/](https://www.geeksforgeeks.org/node-js-constructor-new-vm-script-method/)

`构造器: new vm.Script()`方法创建一个新的`vm.Script`对象并编译所述代码，但它不运行代码。而且，编译了`vm.Script`之后可以根据需要运行任意多次。这里，代码没有连接到任何全局对象，而是在每次运行之前连接，只是为了那个特定的运行。

## 语法:

```js
Constructor: new vm.Script( code, options )
```

## 参数:

该方法接受两个参数，如上所述，如下所述。

*   `code`: 是要编译的 JavaScript 代码。
*   `option`: 是一个可选参数，返回`object`或`string`。如果返回字符串，它定义文件名。

下面的例子说明了`构造函数: new vm.Script()`在 Node.js 中的使用:

## 例 1:

```js
// Node.js program to demonstrate the     
// Constructor: new vm.Script() method

// Including vm and util module
const util = require('util');
const vm = require('vm');

// Creating context
const context = {
  number: 2
};

// Calling the constructor
const script = new vm.Script('Type = "Int"; number *= 2;');

// Contextifying object
vm.createContext(context);

// Calling runInContext method
script.runInContext(context);

// Displays output
console.log(context);
```

**输出:**

```js
{ number: 4, Type: 'Int' }
```

## 例 2:

```js
// Node.js program to demonstrate the     
// Constructor: new vm.Script() method

// Including vm and util module
const util = require('util');
const vm = require('vm');

// Creating context
const context = {
  value: 1.0
};

// Calling the constructor
const script = new vm.Script('Type = "Float"; value += 2*0.1;');

// Contextifying object
vm.createContext(context);

// Calling runInContext method
script.runInContext(context);

// Displays output
console.log(context);
```

**输出:**

```js
{ value: 1.2, Type: 'Float' }
```

**参考:** [https://nodejs.org/api/vm.html#vm_constructor_new_vm_script_code_options](https://nodejs.org/api/vm.html#vm_constructor_new_vm_script_code_options)