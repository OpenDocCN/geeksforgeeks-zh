# JavaScript `Reflect.ownKeys()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-reflect-ownkeys-method/](https://www.geeksforgeeks.org/javascript-reflect-ownkeys-method/)

JavaScript 中的 `Reflect.ownKeys()` 方法用于返回目标对象自身属性键的数组，它忽略继承的属性。

## 语法

```javascript
Reflect.ownKeys( obj )
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `obj`：此参数保存目标对象，用于获取自己的密钥。

## 返回值

这个方法总是返回目标对象自身属性键的数组。

## 异常

当目标不是对象时，类型错误是作为结果给出的异常。

以下示例说明了 JavaScript 中的 `Reflect.ownKeys()` 方法：

### 示例 1

```javascript
const object1 = {
  property1: 332,
  property2: 2
};

const array1 = [];

console.log(Reflect.ownKeys(object1));

console.log(Reflect.ownKeys(array1));

const obj = {ab: 5, bc: 5}; 
const obj1 = {ab: 5, bc: 5, ca:7};

console.log(Reflect.ownKeys(obj));   
console.log(Object.keys(obj1)); 
console.log(Reflect.ownKeys(obj1));
```

**输出：**

```javascript
[ 'property1', 'property2' ]
[ 'length' ]
[ 'ab', 'bc' ]
[ 'ab', 'bc', 'ca' ]
[ 'ab', 'bc', 'ca' ]
```

### 示例 2

```javascript
console.log(Reflect.ownKeys({z: 3, y: 2, x: 1}));
console.log(Reflect.ownKeys([]));

let sym = Symbol.for('comet')
let sym2 = Symbol.for('meteor')
let obj = {[sym]: 0, 'val': 0, '45': 0, 'sdf': 0,
           [sym2]: 0, 'safss': 0, '34': 0, 'val2': 0}
console.log(Reflect.ownKeys(obj));

var obj1 = Object.create({}, { hoo:
    { value: function() { return this.hoo; } } }); 
console.log(Object.keys(obj1));  
console.log(Reflect.ownKeys(obj1));
```

**输出：**

```javascript
[ 'z', 'y', 'x' ]
[ 'length' ]
[
  '34',
  '45',
  'val',
  'sdf',
  'safss',
  'val2',
  Symbol(comet),
  Symbol(meteor)
]
[]
[ 'hoo' ]
```

## 支持的浏览器

JavaScript `Reflect.ownKeys()` 方法支持的浏览器如下：

*   谷歌 Chrome 49 及以上
*   Edge 12 及以上
*   Firefox 42 及以上版本
*   Opera 36 及以上
*   Safari 10 及以上