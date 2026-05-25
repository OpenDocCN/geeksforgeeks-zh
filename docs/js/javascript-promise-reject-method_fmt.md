# JavaScript Promise.reject()方法

> 原文：[https://www.geeksforgeeks.org/javascript-promise-reject-method/](https://www.geeksforgeeks.org/javascript-promise-reject-method/)

Promise 是一个负责在回调函数中做出承诺的对象，它有两种可能的状态，要么**解析**要么**拒绝**。

`Promise.reject()` 方法用于返回被拒绝的 promise 对象，并给出拒绝的原因。它用于调试目的和选择性错误捕获。`catch()`方法可用于将`reject()`方法的输出记录到控制台。

**语法：**

```
Promise.reject(reason)
```

**参数：** 该方法接受如上所述的单个参数，描述如下：

*   `reason`：是承诺被拒绝的原因。

**返回值：** 返回给定原因的拒绝承诺。

下面的例子说明了 `Promise.reject()` 的方法：

### 例 1：

```javascript
<script>
  // Initialize a promise variable and
  // use the reject() method with a
  // reason as a parameter
  var promise = Promise.reject("I am a reason of error");

  // Catch the promise and pass the
  // function for logging the error in console
  promise.catch(function (error) {
    console.log("error");
  });
</script>
```

**输出：**

```
error
```

### 例 2：

```javascript
<script>
  function main() {
    return new Promise(function (resolve, reject) {
      setTimeout(() => {
        // This is the error which is handled
        // according to network requests
        const error = true;
        reject();
      }, 2000);
    });
  }
  main().catch(function () {
    // Only executed if rejects the promise
    console.log("rejected the promise, something wrong happened");
  });
</script>
```

**输出：**

```
rejected the promise, something wrong happened
```

### 例 3：

```javascript
<script>
  function main() {
    return new Promise(function (resolve, reject) {
      num = 100;
      if (num > 50) {
        reject();
      }
    });
  }
  main().catch(function () {
    // Only executed if rejects the promise
    console.log("Not greater than 100");
  });
</script>
```

**输出：**

```
Not greater than 100
```