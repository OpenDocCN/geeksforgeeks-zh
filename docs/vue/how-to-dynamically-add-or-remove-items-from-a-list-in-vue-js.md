# 如何在 Vue.js 中动态添加或删除列表中的项目？

> 原文:[https://www . geeksforgeeks . org/如何从列表中动态添加或删除项目-in-vue-js/](https://www.geeksforgeeks.org/how-to-dynamically-add-or-remove-items-from-a-list-in-vue-js/)

Vue 是一个用于构建用户界面的进步框架。核心库只专注于视图层，并且易于获取和与其他库集成。Vue 还完全能够结合现代工具和支持库为复杂的单页应用程序提供动力。

使用 Vue.js，可以使用 v-model 指令轻松地动态添加或删除列表中的项目。该指令将所有可能性绑定到一个通道。当用户从可用选项列表中选择一个选项时，它会将其添加到值列表中。同样，如果用户取消选择任何选项，它会将其从值列表中删除。

**例:**

```js
<html>
<head>
    <script src=
"https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js">
      </script>
</head>
<body>
    <div id='parent'>
      <h1 style="color: green;">
        GeeksforGeeks
      </h1>

          <p><strong>Favourite Sports:</strong>
          </p>

        <input type="checkbox" id="cricket" 
               value="cricket" v-model="sports">
        <label for="cricket">Cricket</label>
        <input type="checkbox" id="football" 
               value="football" v-model="sports">
        <label for="football">Football</label>
        <input type="checkbox" id="hockey" 
               value="hockey" v-model="sports">
        <label for="hockey">Hockey</label>
        <input type="checkbox" id="badminton"
               value="badminton" v-model="sports">
        <label for="badminton">Badminton</label>
        <input type="checkbox" id="arching" 
               value="arching" v-model="sports">
        <label for="arching">Arching</label>

        <p><strong>Sports You  Like:</strong>
          {{ sports }}
        </p>

    </div>
    <script src='app.js'></script>
</body>
</html>
```