# JavaScript WeakSet.add() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-weakset-add-with-examples/](https://www.geeksforgeeks.org/javascript-weakset-add-with-examples/)

下面是 `WeakSet.add()` 方法的例子。

## 示例

```javascript
<script>
    function gfg() {
        const weakset = new WeakSet();
        const object1 = {};
        weakset.add(object1);
        document.write(weakset.has(object1));
    }
    gfg();
</script>
```

**输出：**

```
true
```

## 定义

`WeakSet.add()` 是 JavaScript 中的一个内置函数，用于在 `WeakSet` 对象的末尾添加一个对象。`WeakSet` 对象允许您在集合中存储弱持有的对象。

## 语法

```
weakSet.add(A);
```

## 参数

它接受参数 `A`，这是一个要添加到 `WeakSet` 对象的值。

## 返回值

返回 `WeakSet` 对象。

## 示例

```
Input: weakset.add(object1);
Output: true
```

### JavaScript 代码展示该函数的工作方式

#### 代码 #1

```javascript
<script>
    // 构造一个 WeakSet 对象
    const weakset = new WeakSet();

    // 构造新对象 object1, object2, object3, object4
    const object1 = {};
    const object2 = {};
    const object3 = {};
    const object4 = {};

    // 将 object1, object2, object3, object4 添加到 WeakSet 对象的末尾
    weakset.add(object1);
    weakset.add(object2);
    weakset.add(object3);
    weakset.add(object4);

    // 打印检查对象是否已被添加
    document.write(weakset.has(object1) + "<br>");
    document.write(weakset.has(object2) + "<br>");
    document.write(weakset.has(object3) + "<br>");
    document.write(weakset.has(object4));
</script>
```

**输出：**

```
true
true
true
true
```

#### 代码 #2

```javascript
<script>
    // 构造一个 WeakSet 对象
    const weakset = new WeakSet();

    // 构造新对象 object1, object2, object3, object4
    const object1 = {};
    const object2 = {};
    const object3 = {};
    const object4 = {};

    // 打印检查对象是否已被添加
    document.write(weakset.has(object1) + "<br>");
    document.write(weakset.has(object2) + "<br>");
    document.write(weakset.has(object3) + "<br>");
    document.write(weakset.has(object4));
</script>
```

**输出：**

```
false
false
false
false
```

这里的输出是 `false`，因为新创建的对象还没有被添加到 `WeakSet()` 对象的末尾。

## 支持的浏览器

*   谷歌 Chrome 36 及以上
*   Firefox 34 及以上版本
*   Apple Safari 9 及以上版本
*   Opera 23 及以上
*   Edge 12 及以上