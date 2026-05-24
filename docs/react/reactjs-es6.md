# 反应物是 6

> 哎哎哎:# t0]https://www . geeksforgeeks . org/reacjs-es 6/

ES6，也称为 ECMA 脚本 2015，是基于 ECMA ECMA 国际公司-262 和 ISO/IEC 1623 的规范和标准化的脚本语言。它是 ECMAScript 语言规范标准的第六版。它的创建是为了标准化 JavaScript 语言，以带来多种实现。它引入了几个新的特性，例如一个新的循环，用于迭代数组、块范围的变量、模板文字，以及更多的变化，使 JavaScript 编程更加容易。ECMA 脚本最常用于客户端脚本，尤其是在万维网中。利用 node.js 编写基于服务器的应用程序和更广泛的服务需求巨大。

**定义:** ES6 是 ECMA 脚本编程语言，2015 年发布了 5 之后的下一个版本。它被用来创建 JavaScript 语言的标准，这样它可以带来多个独立的实现。

**如何使用 ES6？**
ES6 通常很多地方都支持但是有 Internet Explorer 的问题。所以，当你刚开始用 ES6 风格写作时，你不能确定每个人的浏览器是否会以同样的方式运行。

如今，在巴别塔等实用程序的帮助下，ES6 被编译成“常规”的 ES5 语法。Babel 是一个编译器，它有助于将您在 ES6 中编写的开发代码转换为将在您的生产站点上运行的代码，通常还会与 web pack 捆绑和缩小。

**工作:**你写你的“*”。js* 文件，可以使用任何你想要的 ES6 语法。不是直接加载它们，而是建立一个 web 包，用 Babel 加载 js 文件。通常，您会希望运行 webpack-dev-server，因此当您进行更改时，这种情况会自动发生。现在，不是加载 index.js，而是加载 bundle.js，它包含了您所有的代码。

**let 关键字:** ES6 引入了新的 ***let*** 关键字用于声明变量。在 ES6 引入之前，声明变量的唯一方法是使用关键字 ***var*** 。

使用 *var* 关键字声明的变量是功能范围的，而使用 *let* 关键字声明的变量是块范围的。此外，如果使用关键字 *var* 声明，变量在其范围内的顶部被提升，但是当使用 *let* 关键字声明变量时，没有提升。

块作用域意味着将所有的 JavaScript 语句混杂到一个块中。它在一对花括号之间创建一个新的范围，即{}。因此，如果您使用 *let* 关键字声明一个变量，它将不会存在于该循环之外。让我们看一个例子:

```jsx
// ES6 Syntax
for(let i = 0; i < 10; i++) {

   // Prints '0,1,2,.....9'
   console.log(i);
}

// Prints 'undefined'
console.log(i);  
```

```jsx
// ES5 Syntax
for(var i = 0; i < 10; i++) {

   // Prints '0,1,2,.....9'
   console.log(i); 
}

// Prints '10'
console.log(i); 
```

因此，您可以看到 ES6 语法中的变量 ***i*** 在 for 循环之外是不可访问的。这样做的好处是可以多次使用同一个变量名，因为作用域仅限于块，即{}。

**const 关键字:*****const***关键字用于定义常量。常量是只读的，这意味着您不能向它们重新分配任何新值。它们也是块范围的，像 ***让*** 关键词。

```jsx
// Creating a constant variable
const PI = 3.14;

// Prints '3.14'
console.log(PI); 

// Throws an Error
PI = 777; 
```

**示例:**代码说明如何更改对象属性或数组元素，如下所示:

```jsx
// Sample object with some properties
const Branch = {name: "IT", students: 55};

// Prints 'IT'
console.log(Branch.name); 

// Changing the object property value
Branch.name = "CSE";

// Prints 'CSE'
console.log(Branch.name); 
```

```jsx
// Sample array with some values
const Fruits = ["apple", "mango", "banana"];

// Prints 'apple'
console.log(Fruits[0]); 

// Changing array element
Fruits[0] = "grapes";

// Prints 'grapes'
console.log(Fruits[0]); 
```

**for-of 循环:**for-of 循环用于非常容易地迭代数组或任何其他可迭代对象。此外，使用这种类型的循环，循环内可迭代对象的每个元素都会被执行。

**示例:**代码说明如何在 ReactJs 中使用 for-of 循环，如下所示:

```jsx
// Iterating over array
let colors = ["red", "blue", "green", 
        "yellow", "pink", "purple"];

// Using the for-of loop
for (let color of colors) {

   // Prints 'red,blue,green,yellow,pink,purple'
   console.log(color); 
}
```

```jsx
// Iterating over string
let name = "Alpha Charlie";

// Using the for-of loop 
for(let character of name) {

   // Prints 'A,l,p,h,a, ,C,h,a,r,l,i,e'
   console.log(character); 
}
```

**模板文字:**模板文字有助于提供一种简单明了的方式来编写多行字符串并执行字符串插值。它还使得在任何地方将变量或表达式嵌入字符串变得容易。

现在，Back-ticks(` `)字符被用来创建模板文字，而不是单引号和双引号。可以使用模板文字语法将变量和表达式放在字符串中。

**例:**ES6 中多线串的使用。

```jsx
// Multi-line string in ES6
let str = `Jack and Jill
   went up the hill.`;

// Sample values
let a = 30;
let b = 10;

// String with embedded variables
// and expression
let answer = 
  `The difference of ${30} and ${10} is ${a-b}.`;

// Prints 'The difference of 30 and 10 is 20.'
console.log(answer); 
```

**例:**多线串在 ES5 中的使用。

```jsx
// Multi-line string in ES5
var str = 'Jack and Jill\n\t'
   + 'went up the hill.';

// Sample values
var a = 30;
var b = 10;

// Creating string using variables
// and expression
var answer = 'The difference of ' + a 
    + ' and ' + b + ' is ' + (a-b) + '.';

// Prints 'The difference of 30 and 10 is 20.'
console.log(answer); 
```

**箭头功能:**箭头功能使得创建功能变得非常容易。这是一个表达式闭包，可以创建漂亮而紧凑的函数，尤其是在处理回调、列表或错误处理时。

```jsx
// Arrow functions
arr.map((func) => {
  return func + 1;
});
```

此外，如果只传递一个参数，则不需要括号。此外，如果您只返回一个值，则没有括号和 return 语句:

```jsx
arr.map(func => func + 1);
```

如果不使用箭头函数，语法如下:

```jsx
// Without Arrow functions
arr.map(function (func) {
  return func + 1;
});
```