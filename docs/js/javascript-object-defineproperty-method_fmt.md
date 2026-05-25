# JavaScript | `object.defineProperty()`方法

> 原文: [https://www.geeksforgeeks.org/javascript-object-defineproperty-method/](https://www.geeksforgeeks.org/javascript-object-defineproperty-method/)

JavaScript 中的`object.defineProperty()`方法是一个标准的内置对象，它直接在一个对象上定义一个新的属性并返回该对象。

## 语法

```
Object.defineProperty(obj, prop, descriptor)
```

## 参数

该方法接受三个参数，如上所述，如下所述:

*   `obj`: 该参数保存用户将要在其上定义属性的对象。
*   `prop`: 此参数保存将要定义或修改的属性的名称。
*   `descriptor`: 此参数保存正在定义或修改的属性的描述符。

## 返回值

该方法返回作为参数传递给函数的对象。

下面的例子说明了 JavaScript 中的`Object.defineProperty()`方法:

## 例 1

```javascript
<script>
const geek1 = {};
Object.defineProperty(geek1, 'prop1', {
  value: 65,
  writable: false
});
geek1.prop1 = 7;
console.log(geek1.prop1);

const geek2 = {};  
Object.defineProperty(geek2, 'prop2', {
  value: 54,  
  value: 23,  
  value: 12*9,  
  });  
geek2.prop2 ;  
console.log(geek2.prop2); 
</script> 
```

**输出:**

```

```

## 例 2

```javascript
<script>
function gfg() {
}

var result;
Object.defineProperty(gfg.prototype, "valx", {
  get() {
    return result;
  },
  set(valx) {
    result = valx;
  }
});

var vala = new gfg();
var valb = new gfg();
vala.valx = 6;
console.log(valb.valx);

function gfg1() {
}

gfg1.prototype.valx = 4;
Object.defineProperty(gfg1.prototype, "valy", {
  writable: false,
  value: 8
});

var vala = new gfg1();
vala.valx = 4;
console.log(vala.valx); 
console.log(gfg1.prototype.valx); 
vala.valy = 2;
console.log(vala.valy);
console.log(gfg1.prototype.valy);
</script> 
```

**输出:**

```

```

## 支持的浏览器

`object.defineProperty()`方法支持的浏览器如下:

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   旅行队
*   边缘