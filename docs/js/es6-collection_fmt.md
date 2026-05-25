# ES6 集合

> 原文: [https://www.geeksforgeeks.org/es6-collection/](https://www.geeksforgeeks.org/es6-collection/)

ES6 是 JavaScript 中添加的一系列新功能。在 ES6 版本中，包含了新的数据类型集合，因此不再需要使用对象，并且以简单的方式实现事情变得更加容易。
在 ES6 版本中，JavaScript 引入了两个新东西。

*   Map
*   Set

## Map

Map 是任何类型的键和值的集合，简单来说 Map 是键-值对的集合。它像 JavaScript 中的一个对象一样工作。它返回一个新的或空的 Map。

**语法:**

```
var map = new Map();
```

| **方法** | **描述** |
| :--- | :--- |
| `map.size()` | 它确定 Map 中键值对的数量。 |
| `map.set()` | 它设置键的值。它需要两个参数，键和键的值。 |
| `map.has()` | 它检查 Map 中是否存在某个键，然后返回 `true`。 |
| `map.get()` | 它获取与键关联的值。如果值不存在，则返回 `undefined`。 |
| `map.keys()` | 它返回一个包含 Map 中所有键的迭代器。 |
| `map.entries()` | 它返回一个新的迭代器数组，其中包含按插入顺序排列的每个元素的键值对。 |
| `map.values()` | 它返回一个包含 Map 中每个值的迭代器。 |
| `map.delete()` | 用于删除一个条目。 |
| `map.clear()` | 它从 Map 中清除所有键值对。 |
| `map.forEach()` | 它执行一个 `callback` 函数。此函数为 Map 中的每个元素执行。 |

## for...of 循环

`for...of` 是一个循环，它提供了一个非常简洁的语法来迭代所有种类的可迭代对象。这个循环迭代数组、字符串、类似数组的对象、类型化数组、Map 和任何用户定义的可迭代对象。

*   **例:**

```javascript
// Simple JavaScript program to illustrate for...of loop
var arr = ['a', 3 , 'b', 2 , 'c', 1 ,'d'];
document.write("array elements are : ");
for (let ele of arr) {
  document.write(ele+' ');
}
```

*   **输出:**

```
array elements are : a 3 b 2 c 1 d
```

## Map 示例

### 程序 1: 实现 `map.size()`，`map.set()` 方法

```javascript
// Simple JavaScript program to implement Map.size
var m = new Map()
m.set('a', 1);
m.set('b', 2);
m.set('c', 3);
document.write(m.size);
```

*   **输出:**

```
size of the map is : 3
```

### 程序 2: 实现 `map.set()`，`map.get()`，`map.delete()`，`map.clear()`，`map.has()` 方法

```javascript
// Simple JavaScript program with Map
var map = new Map();
map.set("website ", "Geeksforgeeks");
document.write("Website is - " +map.get("website "));
// Use "get()" function

map.set("Subject1", "JavaScript"); //use "set()" function
map.set("Subject2", "C++");
map.set("Subject3", "python");
document.write("<br>Is it contains JavaScript ? - "+map.has("Subject1"));
document.write("<br>Is it contains C++ ? - "+map.has("Subject2"));
document.write("<br>Is it contains python ? - "+map.has("Subject3"));
// Use "has()" function

map.delete("subject2");
document.write("<br>Delete C++");
// Use "delete()" function
document.write("<br>Is is contains C++ now ? - "+map.has("C++")); //false

map.clear();//use "clear()" function
document.write("<br>Delete whole map");
document.write("<br> Is it has any value now? - "+map.has("Subject1"));
```

*   **输出:**

```
Website is - Geeksforgeeks
Is it contains JavaScript ? - true
Is it contains C++ ? - true
Is it contains python ? - true
Delete C++
Is is contains C++ now ? - false
Delete whole map
Is it has any value now? - false
```

### 程序 3: 实现 `map.forEach()` 方法

```javascript
// Simple JavaScript program to implement Map.forEach()
var m = new Map()
m.set('a', 1);
m.set('b', 2);
m.set('c', 3);
m.forEach((k, v)=>document.write(`key: ${k} value: ${v} <br>`));
```

*   **输出:**

```
key: 1 value: a
key: 2 value: b
key: 3 value: c
```

### 程序 4: 实现 `map.keys()` 方法

```javascript
// Simple JavaScript program to implement Map.keys()
var m = new Map()
m.set('a', 1);
m.set('b', 2);
m.set('c', 3);
var i = m.keys();
document.write("value : "+ i.next().value+"<br>");//"a"
document.write("value : "+ i.next().value+"<br>");//"b"
document.write("value : "+ i.next().value+"<br>");//"c"
document.write("value : "+ i.next().value+"<br>");//undefined
// Because the map contains only 4 elements
```

*   **输出:**

```
value : a
value : b
value : c
value : undefined
```

### 程序 5: 实现 `map.entries()` 方法

```javascript
// Simple JavaScript program to implement Map.entries()
var m = new Map()
m.set('a', 1);
m.set('b', 2);
m.set('c', 3);
var i = m.entries();
document.write("value : "+ i.next().value+"<br>");//"a,1"
document.write("value : "+ i.next().value+"<br>");//"b,2"
document.write("value : "+ i.next().value+"<br>");//"c,3"
document.write("value : "+ i.next().value+"<br>");//undefined
// Because the map contains only 4 elements
```

*   **输出:**

```
value : a,1
value : b,2
value : c,3
value : undefined
```

### 程序 6: 实现 `map.values()` 方法

```javascript
// Simple JavaScript program to implement Map.values()
var m = new Map()
m.set('a', 1);
m.set('b', 2);
m.set('c', 3);
var i = m.values();
document.write("value : "+ i.next().value+"<br>");//"1"
document.write("value : "+ i.next().value+"<br>");//"2"
document.write("value : "+ i.next().value+"<br>");//"3"
document.write("value : "+ i.next().value+"<br>");//undefined
// Because the map contains only 4 elements
```

*   **输出:**

```
value : 1
value : 2
value : 3
value : undefined
```

## WeakMap

WeakMap 与正常 Map 相似。WeakMap 用于将弱对象引用存储为关键字，即关键字必须是对象。WeakMap 不能被清除，键值可以是垃圾值。

*   **例:**

```javascript
// Simple JavaScript program to implement WeakMap()
var gfg = new WeakMap();
var gg = {};

//"gg" is a object
// Works as key
gfg.set(gg,"c++");
document.write(gfg.has(gg));//true
document.write("<br>"+gfg.get(gg));//c++
gg=null;//"gg" becomes null
document.write("<br>"+gfg.get(gg));//undefined
```

*   **输出:**

```
true
c++
undefined
```

## Set

Set 是 ES6 版本引入的数据结构。一个 Set 是一个像数组一样的值的集合，但是它不包含任何重复。它是可变的，所以我们的程序可以随时添加和删除值。返回 Set 对象。

| **方法** | **描述** |
| :--- | :--- |
| `set.size()` | 它返回集合中存在的值的总数。 |
| `set.add()` | 如果集合中没有该值，则将该值添加到集合中。 |
| `set.clear()` | 它从集合中移除所有值。 |
| `set.delete(v)` | 它从集合中移除一个作为参数传递的值。 |
| `set.has(v)` | 如果传递的值 `v` 在集合中，此方法返回 `true`。 |
| `set.entries()` | 它返回一个迭代器对象，该对象包含一个数组，该数组包含此集合的条目。 |
| `set.values()` 和 `set.keys()` | 它们都从 Set 中返回所有值，类似于 `map.values()`。 |
| `set.forEach()` 方法 | 像 `map.forEach()` 一样，它执行一个回调函数。此函数为集合中的每个元素执行。 |

*   **语法:**

```
var s = new Set("val1","val2","val3")
```

*   **例:**

```javascript
// Simple JavaScript program with Set
var st = new Set();

st.add("JavaScript").add("C++").add("python"); //use "add()" function

document.write("<br>Is it contains JavaScript ? - "+st.has("JavaScript"));
document.write("<br>Is it contains C++ ? - "+st.has("C++"));
document.write("<br>Is it contains python ? - "+st.has("python"));
// Use "has()" function

st.delete("C++");
document.write("<br>Delete C++");

// Use "delete()" function
document.write("<br>Is is contains C++ now ? - "+st.has("C++")); //false

st.clear();//use "clear()" function
document.write("<br>Delete whole set");
document.write("<br> Is it has any value now? - "+st.has("JavaScript"));
```

*   **输出:**

```
Is it contains JavaScript ? - true
Is it contains C++ ? - true
Is it contains python ? - true
Delete C++
Is is contains C++ now ? - false
Delete whole set
Is it has any value now? - false
```

## 迭代器

集合中的迭代器允许一次访问一个对象集合。它与 `next()` 方法一起工作，当调用 `next()` 时，一次打印一个集合的值，并且在成功读取集合的值后，返回属于 `done` 属性的布尔值 `true`。这件事是在控制台窗口发生的。在输出的情况下，如果我们使用关键字 `value` 后跟 `next()`，就像 `iterator.value`，只会显示值。

*   **例:**

## Java 描述语言

```
<script>
// Simple JavaScript program with Set iterator
var s = new Set(['a','b','c']); //set elements
var itr = s.values();
document.write(itr.next().value+"<br>");
document.write(itr.next().value+"<br>");
document.write(itr.next().value+"<br>");
document.write(itr.next().value);//undefined
</script>
```

*   **输出:**

```
a
b
c
undefined
```

**弱集:** 类似于弱地图，也用于存储对象的集合。它类似于正常集，因此不能存储副本。它可能包含垃圾值。集合和弱集合的唯一区别是弱集合包含对象。

*   **例:**

### Java 描述语言

```
<script>
var gfg = new WeakSet
var gg1 = {};//"gg1" is a object
var gg2 = {};//"gg2" is a object

gfg.add(gg1);
gfg.add(gg2);
document.write(gfg.has(gg1));//true
gfg.delete(gg1);//delete "gg1"
document.write("<br>"+gfg.has(gg1));//undefined
</script>
```

*   **输出:**

```
true
false
```