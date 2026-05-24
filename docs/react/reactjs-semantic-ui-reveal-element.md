# 反应语义用户界面显示元素

> 原文:[https://www . geeksforgeeks . org/reactjs-semantic-ui-reveal-element/](https://www.geeksforgeeks.org/reactjs-semantic-ui-reveal-element/)

语义用户界面是一个现代框架，用于为网站开发无缝设计，它给用户一个轻量级的组件体验。它使用预定义的 CSS、JQuery 语言来整合到不同的框架中。

ReactJS Semantic UI 中的显示元素用于通过将鼠标悬停在前面的内容上来显示内容。

**属性:**

*   **移动:**元素向显示内容的方向移动。
*   **旋转:**元素向显示内容的方向旋转。

**状态:**

*   **活动:**显示其隐藏内容。
*   **禁用:**鼠标悬停时不动画。

**语法:**

```jsx
<reveal>
  <reveal.content/>
</reveal>
```

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

*   **第三步:**在给定的目录下安装语义 UI。

    ```jsx
    npm install semantic-ui-react semantic-ui-css
    ```

**项目结构**:如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**示例 1:** 在本例中，我们将使用带有动画道具和小渐变内容类型的展示组件，以便可以通过使用语义 UI 展示元素在交互之前看到内容。

## App.js

```jsx
import React from 'react'
import { Image, Reveal, List } from 'semantic-ui-react'

const styleLink = document.createElement("link");
styleLink.rel = "stylesheet";
styleLink.href = 
"https://cdn.jsdelivr.net/npm/semantic-ui/dist/semantic.min.css";
document.head.appendChild(styleLink);

const Btt = () => (
<div>
    <br />
    <Reveal animated='small fade'>
    <Reveal.Content visible>
      <Image src=
'https://react.semantic-ui.com/images/wireframe/square-image.png'
             size='small' />
    </Reveal.Content>
    <Reveal.Content hidden>
      <Image src=
'https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg'
             size='small' />
    </Reveal.Content>
  </Reveal>
</div>
)

export default Btt
```

**运行应用程序的步骤:**使用以下命令从项目的根目录运行应用程序。

```jsx
npm start
```

**输出:**

![](img/b481aa1fd8bb27d8bec30b411b89b12f.png)

**示例 2:** 在本例中，我们将使用带有动画道具的展示组件，并向右移动类型，以便元素可以向右移动，通过使用语义用户界面展示元素来展示内容。

## App.js

```jsx
import React from 'react'
import { Image, Reveal, List } from 'semantic-ui-react'

const styleLink = document.createElement("link");
styleLink.rel = "stylesheet";
styleLink.href = 
"https://cdn.jsdelivr.net/npm/semantic-ui/dist/semantic.min.css";
document.head.appendChild(styleLink);

const Btt = () => (
<div>
    <br />
    <Reveal animated='move right'>
    <Reveal.Content visible>
      <Image src=
'https://react.semantic-ui.com/images/wireframe/square-image.png' 
             size='small' />
    </Reveal.Content>
    <Reveal.Content hidden>
      <Image src=
'https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg'
       size='small' />
    </Reveal.Content>
  </Reveal>
</div>
)

export default Btt
```

**运行应用程序的步骤:**使用以下命令从项目的根目录运行应用程序。

```jsx
npm start
```

**输出:**

![](img/66cf4f749f5a3a1f208b567b88510c85.png)

**参考:**T2】https://react.semantic-ui.com/elements/reveal