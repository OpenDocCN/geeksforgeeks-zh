# Node.js URLSearchParams.keys()

> 哎哎哎:# t0]https://www.geeksforgeeks.org/node-js-urlsearchparams-keys/

在`URLSearchParams`接口中，`keys()`方法返回一个迭代器，它允许我们遍历对象中存在的所有键。

**语法:**

```js
searchParams.keys();
```

**返回:** 返回每个名称-值对名称的ES6迭代器。

**例 1:**

```js
var searchParams = new URLSearchParams("keyA=valueA&keyB=valueB");

// Display the key/value pairs 
for(var key of searchParams.keys()) { 
  console.log(key); 
}
```

**输出:**

```js
keyA
keyB
```

**范例 2:**

```js
var searchParams = new URLSearchParams("name=john&age=18");

// Display the key/value pairs 
for(var key of searchParams.keys()) { 
  console.log(key); 
}
```

**输出:**

```js
name
age
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari