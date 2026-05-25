# JavaScript EvalError 对象

> 原文：[https://www.geeksforgeeks.org/javascript-evalerror-object/](https://www.geeksforgeeks.org/javascript-evalerror-object/)

我们在 JavaScript 中会遇到几种类型的错误，例如[语法错误](https://www.geeksforgeeks.org/javascript-syntaxerror-return-not-in-function/)、[范围错误](https://www.geeksforgeeks.org/javascript-rangeerror-precision-is-out-of-range/)、[引用错误](https://www.geeksforgeeks.org/javascript-referenceerror-reference-to-undefined-property-x/)、评估错误等。`EvalError`表示关于全局`eval()`函数的错误。

然而，新版本的 JavaScript 不会抛出`EvalError`。

## 语法

```
new EvalError()
new EvalError(message)
```

## 参数

`message`是一个可选参数，提供了所发生异常的详细信息。

## 返回值

新构造的`EvalError`对象。

以下是一些 JavaScript `EvalError`的例子。

## 例 1

```javascript
<script>
  try {
    throw new EvalError('EvalError has occurred');
  } catch (e) {
    console.log(e instanceof EvalError); 
    console.log(e.message);             
    console.log(e.name);                
  }
</script>
```

**输出：**

```
true
EvalError has occured
EvalError
```

## 例 2

```javascript
var score={
  checkerror:function (score){
    if(score<0)
    {
       try{
         throw new EvalError('Error occurred');
       }catch(e)
       {
          console.log(e.message); 
       }
    }
  }
}
console.log(score.checkerror(-3));
```

**输出：**

```
Error occurred
undefined
```