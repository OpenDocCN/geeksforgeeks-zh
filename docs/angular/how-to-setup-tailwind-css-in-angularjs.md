# 如何在 AngularJS 中设置顺风 CSS？

> 原文:[https://www . geesforgeks . org/how-setup-tail wind-CSS-in-angular js/](https://www.geeksforgeeks.org/how-to-setup-tailwind-css-in-angularjs/)

**什么是顺风 CSS？**

根据官方文档，Tailwind CSS 是一个实用程序优先的 CSS 框架，用于快速构建自定义用户界面。这是一种很酷的方式来编写内联样式并实现一个令人敬畏的界面，而无需编写一行自己的 CSS。

**什么是棱角分明？**

Angular 是一个使用 HTML 和 TypeScript 构建单页客户端应用程序的平台和框架。Angular 是用 TypeScript 编写的。它将核心和可选功能实现为一组导入应用程序的类型脚本库。

所以让我们从创建一个新的角度项目开始，并在角度项目中设置顺风 CSS。

**设置新的角度项目:**

*   Open CMD (window) or terminal (Linux) and write the command.

```ts
ng new project-name
```

*   After running the above command, it will ask some questions as shown below, which are related to CSS, basically the CSS type you want to use in your perspective project. Let's choose CSS for this project.
*   It also requests the route to enable it by saying "yes".

让他们完成上面的过程。

*   Once the process is completed, there is a project folder. Use CMD or terminal change directory command to enter the folder and run the following command.

```ts
ng serve --open
```

*   It opens the angular of the default page in the browser.

角度设置完成，让我们移动到角度安装顺风 CSS。

**在角度项目中安装顺风 CSS:**在角度项目中添加顺风 CSS 有 2 种方式。

*   Use CDN
*   Use PostCSS and command line configuration

**使用 CDN:**

*   Open the project in your favorite code editor.
*   Browse the angular index.html project.
*   Just paste the following lines on the head.

> <链接 href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css【rel = "样式表">

它将包括项目中所有使用互联网的顺风图书馆。这是一种包含顺风的简单方法。

**注:**要求互联网。如果互联网不可用，那么它将无法工作。

**使用 PostCSS:**

*   Open the project directory in cmd or terminal and run the following command.

```ts
npm install tailwindcss postcss autoprefixer
```

*   The above command installation requires the library to run in the downwind. Let's configure downwind css and postwind css. Therefore, we can create a file named *tailwind.config.js* and *postss.config.js* in the project file.

*T2T4*

```ts
*module.exports = {
    purge: [],
    darkMode: false, // or 'media' or 'class'
    theme: {
        extend: {},
    },
    variants: {
        extend: {},
    },
    plugins: [],
}* 
```

***postscript . config . js***

```ts
module.exports = {
    plugins: {
        tailwindcss: {},
        autoprefixer: {},
    },
};

```

*   Now the downwind css is ready to be used in your Angular project, and it has been successfully set into the project.

现在你可以使用 tailwind 内嵌 CSS，为了让你的手更脏，你可以参考 tailwind 网站。

*参考:*[https://taiwindcss . com/](https://tailwindcss.com/)