# 自举-5 种形式

> 原文:[https://www.geeksforgeeks.org/bootstrap-5-forms/](https://www.geeksforgeeks.org/bootstrap-5-forms/)

**表单控件:** *<输入>、<选择>、<文本区>* 是用于常规外观的标签，如输入字段、选择项目和文本区。

**注意:**为使用户界面更加像样，根据需要使用*填充、边距*等属性。

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <!-- CSS only -->
    <link rel="stylesheet" href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css">
</head>

<body class="container-sm mt-5">
    <form>
        <h2 class="text-center">
            Display Form Controls
        </h2>

        <div class="form-group">
            <label>Email address</label>
            <input type="email" class="form-control"
                placeholder="geeks@example.com">
        </div>
        <div class="form-group mt-2">
            <label>Example select</label>
            <select class="form-control">
                <option>1</option>
                <option>2</option>
                <option>3</option>
                <option>4</option>
                <option>5</option>
            </select>
        </div>
        <div class="form-group mt-2">
            <label>Example textarea</label>
            <textarea class="form-control"></textarea>
        </div>
    </form>
</body>

</html>
```