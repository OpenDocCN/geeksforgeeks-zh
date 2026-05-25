# JavaScript TypeError – 属性“X”不可配置，不能删除

> 原文: [https://www.geeksforgeeks.org/javascript-typeerror-property-x-is-non-configurable-and-cant-be-deleted/](https://www.geeksforgeeks.org/javascript-typeerror-property-x-is-non-configurable-and-cant-be-deleted/)

这个 JavaScript 异常 **“属性是不可配置的”** 在用户试图删除一个不可配置的属性时发生。

**消息:** `TypeError: Calling delete on 'prop2' is not allowed in strict mode` 或类似信息。

**错误类型:**

```
TypeError
```

**错误原因:** 试图删除不可配置的属性。

## 示例 1

在本例中，`delete` 用于删除不可配置的属性，因此出现了错误。

```html
<script>
    'use strict';
    var GFG_Obj = Object.freeze({prop1: 'val1', prop2: 123});
    delete GFG_Obj.prop2;  // Error here
</script>
```

**输出 (控制台):**

```
TypeError: Calling delete on 'prop2' is not allowed in strict mode
```

## 示例 2

在本例中，`delete` 用于删除 `Math.PI`，这是一个不可配置的属性，所以出现了错误。

```html
<script>
    'use strict';
    delete Math.PI;  // Error here
</script>
```

**输出 (控制台):**

```
TypeError: Calling delete on 'PI' is not allowed in strict mode
```