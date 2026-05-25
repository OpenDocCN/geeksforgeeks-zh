# Node.js URLSearchParams API

> 哎哎哎:# t0]https://www . geeksforgeeks . org-node-js-urlsearchparams-API/

Node.js 是一个开源项目，广泛用于动态 web 应用程序的开发。Node.js 中的 `URLSearchParams` API 允许对 URL 查询进行读写操作。

`URLSearchParams` 类是一个全局对象，与以下四个构造函数之一一起使用。

## 构造函数

1.  **`new URLSearchParams()`**: 无参数构造函数实例化新的空 `URLSearchParams` 对象。
2.  **`new URLSearchParams(string)`**: 接受一个字符串作为参数来实例化一个新的 `URLSearchParams` 对象。

```js
var params = new URLSearchParams('user=abc&q=xyz');
console.log(params.get('user'));
console.log(params.get('q'));
```

**输出:**

```js
abc
xyz
```

3.  **`new URLSearchParams(obj)`**: 接受一个具有键值对集合的对象来实例化一个新的 `URLSearchParams` 对象。`obj` 的键值对总是被强制转换为字符串。不允许重复的键。

```js
const params = new URLSearchParams({
  user: 'ana',
  course: ['math', 'chem', 'phys']
});
console.log(params.toString());
```

**输出:**

```js
user=ana&course=math%2Cchem%2Cphys
```

4.  **`new URLSearchParams(iterable)`**: 接受一个具有键值对集合的可迭代对象来实例化一个新的 `URLSearchParams` 对象。`iterable` 可以是任何可迭代对象。由于 `URLSearchParams` 本身是可迭代的，所以一个可迭代对象可以是另一个 `URLSearchParams`，此时构造函数将创建所提供 `URLSearchParams` 的克隆。允许重复的键。

```js
// Using a Map object as it is iterable
const map = new Map();
map.set('West Bengal', 'Kolkata');
map.set('Karnataka', 'Bengaluru');
params = new URLSearchParams(map);
console.log(params.toString());
```

**输出:**

```js
West+Bengal=Kolkata&Karnataka=Bengaluru
```

## 访问查询参数

*   **`urlSearchParams.get(name)`**: 返回与传入参数匹配的第一个名称-值对的值。如果不存在这样的对，则返回 `null`。

```js
const myURL = new URL(
  'https://example.org/?abc=123&abc=526');

console.log(myURL.searchParams.get('abc'));
```

**输出:**

```js
'123'
```

*   **`urlSearchParams.getAll(name)`**: 返回与传入参数匹配的所有名称-值对的值。如果不存在这样的对，则返回 `null`。

```js
const myURL = new URL(
  'https://example.org/?abc=123&abc=526');
console.log(myURL.searchParams.getAll('abc'));
```

**输出:**

```js
[ '123', '526' ]
```

*   **`urlSearchParams.has(name)`**: 如果传入的参数与任何现有的名称-值对的名称匹配，则返回 `true`，否则返回 `false`。

```js
const myURL = new URL(
  'https://example.org/?abc=123&xyz=526');
console.log(myURL.searchParams.has('abc'));
console.log(myURL.searchParams.has('pqr'));
```

**输出:**

```js
true
false
```

## 操纵查询参数

*   **`urlSearchParams.set(name, value)`**: 将 `URLSearchParams` 对象中与 `name` 关联的值设置为指定的 `value`。如果存在多个名称与 `name` 参数相同的名称-值对，则只有第一个匹配对的值会被更改，其余所有对都会被移除。

```js
const params = new URLSearchParams(
    'abc=123&xyz=526&abc=258');
console.log(params.toString());
params.set('abc', 'opq');
console.log(params.toString());
```

**输出:**

```js
abc=123&xyz=526&abc=258
abc=opq&xyz=526
```

*   **`urlSearchParams.append(name, value)`**: 向现有的 `URLSearchParams` 查询追加一个新的名称-值对。

```js
const params = new URLSearchParams('xyz=123');
params.append('foo', '789');
params.append('xyz', 'zoo');
params.append('foo', 'def');
console.log(params.toString());
```

**输出:**

```js
xyz=123&foo=789&xyz=zoo&foo=def
```

*   **`urlSearchParams.delete(name)`**: 删除所有名称与 `name` 参数相同的名称-值对。

```js
const params = new URLSearchParams(
  'xyz=123&foo=789&xyz=zoo&foo=def');
console.log(params.toString());
params.delete('foo');
console.log(params.toString());
```

**输出:**

```js
xyz=123&foo=789&xyz=zoo&foo=def
xyz=123&xyz=zoo
```

*   **`urlSearchParams.sort()`**: 使用稳定的排序算法，按名称就地对现有的名称-值对进行排序。

```js
const params = new URLSearchParams(
  'query=node&type=search&abc=programs');
params.sort();
console.log(params.toString());
```

**输出:**

```js
abc=programs&query=node&type=search
```

*   **`urlSearchParams.toString()`**: 将 URL 查询参数作为字符串返回，必要时对字符进行百分比编码。

```js
const params = new URLSearchParams(
  'query=node&type=search&passwd[]=3456');
console.log(params.toString());
```

**输出:**

```js
query=node&type=search&passwd%5B%5D=3456
```

## 迭代查询参数

*   **`urlSearchParams.entries()`**: 返回一个遍历参数对象条目集的迭代器。

```js
const params = new URLSearchParams(
    'query=node&type=search&passwd=3456');
for(var pair of params.entries()) {
   console.log(pair[0]+ '-->'+ pair[1]); 
}
```

**输出:**

```js
query-->node
type-->search
passwd-->3456
```

*   **`urlSearchParams.keys()`**: 返回一个遍历参数对象键集的迭代器。

```js
const params = new URLSearchParams(
    'query=node&type=search&passwd=3456');
for(var key of params.keys()) {
   console.log(key); 
}
```

**输出:**

```js
query
type
passwd
```

*   **`urlSearchParams.values()`**: 返回一个遍历参数对象值集的迭代器。

```js
const params = new URLSearchParams(
    'query=node&type=search&passwd=3456');
for(var value of params.values()) {
   console.log(value); 
}
```

**输出:**

```js
node
search
3456
```

*   **`urlSearchParams.forEach(fn[, arg])`**: `fn` 是一个为查询中的每个名称-值对调用的函数，`arg` 是在调用 `fn` 时要使用的对象。它遍历查询中的每个名称-值对并调用该函数。

```js
const myURL = new URL(
  'https://example.com/?a=b&c=d&d=z');
myURL.searchParams.forEach(
  (value, name, searchParams) => {
    console.log(name, value, 
      myURL.searchParams === searchParams);
  });
```

**输出:**

```js
a b true
c d true
d z true
```

*   **`urlSearchParams[Symbol.iterator]()`**:

```js
const params=new URLSearchParams(
    'firstname=john&lastname=beck&gender=male');
for (const [name, value] of params) {
  console.log(name, value);
}
```

**输出:**

```js
firstname john
lastname beck
gender male
```