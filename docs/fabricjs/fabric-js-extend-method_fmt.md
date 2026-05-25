# Fabric.js extend()方法

> 原文: [https://www.geeksforgeeks.org/fabric-js-extend-method/](https://www.geeksforgeeks.org/fabric-js-extend-method/)

`extend()`方法用于在目标对象上创建源对象所有属性的副本，并返回目标对象。不要克隆或扩展结构。对象子类。这主要是为了内部使用，对 fabricJS 对象有额外的处理，它在深度克隆中跳过了画布属性。

## 语法

```javascript
extend(destination, source)
```

## 参数

该方法接受两个参数，如上所述，如下所述:

*   `destination`: 此参数表示复制到哪里。
*   `source`: 此参数表示从哪里复制。

## 返回值

该方法返回源对象在目标对象上的所有属性的副本，并返回目标对象。

## 示例1

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js.map"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.js"></script>
</head>

<body>
    <script type="text/javascript">
        var obj1 = {
            key1: 'Geeks',
        };

        var obj2 = {
            key2: 'GeeksforGeeks',
        };

        console.log(fabric.util.object.extend(obj1, obj2));
    </script>
</body>

</html>
```

## 输出

```json
{"key1": "Geeks", "key2": "GeeksforGeeks"}
```

## 示例2

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js.map"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.js"></script>
</head>

<body>
    <script type="text/javascript">
        var obj1 = {
            key1: 'GFG', key2: 'gfg',
        };

        var obj2 = {
            key3: '5', key4: '10',
        };

        console.log(fabric.util.object.extend(obj1, obj2));
    </script>
</body>

</html>
```

## 输出

```json
{"key1": "GFG", "key2": "gfg", "key3": "5", "key4": "10"}
```