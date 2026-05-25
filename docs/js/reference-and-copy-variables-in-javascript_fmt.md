# 在 JavaScript 中引用和复制变量

> 原文：[https://www.geeksforgeeks.org/reference-and-copy-variables-in-javascript/](https://www.geeksforgeeks.org/reference-and-copy-variables-in-javascript/)

## 按值传递与按引用传递概述

在本文中，我们将讨论 JavaScript 中的按值传递和按引用传递。
JavaScript 总是通过值传递，但是在数组或对象中，值是对它的引用，所以你可以“改变”数据。JavaScript 有 5 种通过值传递的原始数据类型，它们是 `boolean`、`null`、`undefined`、`string` 和 `number`。它有 3 种通过引用传递的非原语数据类型，分别是 `array`、`function`、`object`。在非原始数据类型中，我们在复制数据方面面临一些挑战。正如我们所知，对象是在计算机内存的某个地方创建的。当我们声明任何属性时，它会在内存中创建一个空间。

**示例：** 地址是一种数据类型，通过值传递，就像数字、字符串和地址指向内存中的位置一样。

## 原始数据类型的按值传递

### 数字情况下按值传递

```javascript
let age = 100;
let age2 = age;
document.write(age, age2);
document.write("<br>");
age = 200;
document.write(age, age2);
```

**输出：**

```
100 100
200 100
```

### 字符串情况下按值传递

```javascript
let name = 'sam';
let name2 = name;
document.write(name, name2);
document.write("<br>");
name = 'xyz';
document.write(name, name2);
```

**输出：**

```
sam sam
xyz sam
```

## 非原始数据类型的按引用传递

### 数组情况下通过引用

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const team = players;
document.write(players, team);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "Ryan", "Poppy"]
```

现在，如果您更改“团队”数组中的数据，它也会影响“玩家”数组

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const team = players;
team[3] = 'xyz';
document.write(players, team);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "Ryan", "xyz"]
```

这是数组引用，不是数组副本。它们都指向同一个数组。

## 复制数组的四种方法

我们有 4 种方法可以做到。通过使用这些方法，主阵列不会改变。

### 1. 使用 `slice()` 方法

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const playersCopy = players.slice();
playersCopy[2]="west";
console.log(players, playersCopy);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "west", "Poppy"]
```

### 2. 使用 `concat()` 方法

创建一个新的数组变量，然后将旧数组连接到新数组中。

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const playersCopy2 = [].concat(players);
playersCopy2[2]='hell';
document.write(players, playersCopy2);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "hell", "Poppy"]
```

### 3. 使用 ES6 展开运算符

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const playersCopy3 = [...players];
playersCopy3[3] = 'heeee hawww';
document.write(players, playersCopy3);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "Ryan", "heeee hawww"]
```

### 4. 使用 `Array.from()`

```javascript
const players = ['Sam', 'Sarah', 'Ryan', 'Poppy'];
const playersCopy4 = Array.from(players);
playersCopy4[3]="kim";
document.write(players, playersCopy4);
```

**输出：**

```
["Sam", "Sarah", "Ryan", "Poppy"]
["Sam", "Sarah", "Ryan", "kim"]
```

## 对象中的引用

同样的点也适用于对象，它也会影响原始对象。

```javascript
const person = {
      name: 'loren isum',
      age: 80
    };
const captain = person;
person.age = 25;
console.log(captain, person);
```

**输出：**

```
{name: "loren isum", age: 25}
{name: "loren isum", age: 25}
```

## 复制对象的两种方法

### 1. 使用 `Object.assign()` 方法

```javascript
const personObject = {
      name: 'loren isum',
      age: 80
    };
const personCopy = Object.assign({},
    personObject, { number: 99, age: 12 });
personCopy.age = 78;
console.log(personCopy, personObject);
```

**输出：**

```
{name: "loren isum", age: 78, number: 99}
{name: "loren isum", age: 80}
```

### 2. 使用展开运算符

```javascript
const personData = {
      name: 'loren isum',
      age: 80
    };
const personCopy2 = {...personData };
personCopy2.age = 78;
console.log(personCopy2, personData );
```

**输出：**

```
{name: "loren isum", age: 78}
{name: "loren isum", age: 80}
```

## 相等运算符与引用类型

还有一件事你需要考虑一下，在一个等式和等式运算符的情况下会发生什么。当我们在引用类型变量上使用这些运算符时，它们会检查引用。如果属性引用了同一个项目，那么比较将输出“真”，否则返回“假”。

```javascript
var arrayReference = ["Hi!"];
var arrayCopy = arrayReference;
console.log(arrayCopy === arrayReference);
```

**输出：**

```
true
```

```javascript
var array1 = ['Hi!'];
var array2 = ['Hi!'];
console.log(array1 === array2);
```

**输出：**

```
false
```

这可以通过字符串化数组来纠正。

```javascript
var arr1str = JSON.stringify(array1);
var arr2str = JSON.stringify(array2);
console.log(arr1str === arr2str); // true
```

**输出：**

```
true
```

我们可以更改对象人的名称属性，但由于引用人已被标记为 `const`，因此无法重置引用人。

```javascript
const person = {
   name: 'Tammy'
};

// Name property changed
person.name = 'abc';

// Objects are a reference type
var val1 = { name: "Tom" };
   var val2 = { name: "Tom" };
   console.log(val1 == val2)
```

**输出：**

```
false
```

但是我们可以通过字符串化数组来纠正这个问题。

```javascript
var array1 = ['Hi!'];
var array2 = ['Hi!'];
var arr1str = JSON.stringify(array1);
var arr2str = JSON.stringify(array2);
console.log(arr1str === arr2str);
```

**输出：**

```
true
```

## 函数中的按引用传递

如果我们在函数中传递对象，它会改变两个对象。

```javascript
function changevalue(person) {
    var newPersonObj = (person);
    newPersonObj.age = 25;
    return newPersonObj;
}
var alex = {
    name: 'xyz',
    age: 30
};
var alexChanged = changevalue(alex);
console.log(alex);
console.log(alexChanged);
```

**输出：**

```
{ name: 'xyz', age: 25 }
{ name: 'xyz', age: 25 }
```

我们可以通过解析和字符串化对象来解决这个问题。

```javascript
function changevalue(person) {
    var newPersonObj = JSON.parse(JSON.stringify(person));
    newPersonObj.age = 25;
    return newPersonObj;
}
var alex = {
    name: 'xyz',
    age: 30
};
var alexChanged = changevalue(alex);
console.log(alex);
console.log(alexChanged);
```

**输出：**

```
{ name: 'xyz', age: 30 }
{ name: 'xyz', age: 25 }
```