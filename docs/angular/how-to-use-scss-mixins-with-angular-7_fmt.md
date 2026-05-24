# 如何在 Angular 7 中使用 SCSS Mixins？

> 原文：[https://www.geeksforgeeks.org/how-to-use-scss-mixins-with-angular-7/](https://www.geeksforgeeks.org/how-to-use-scss-mixins-with-angular-7/)

使用 [Angular CLI](https://www.geeksforgeeks.org/angular-cli-angular-project-setup/) 时，默认样式表具有 `.css` 扩展名。

## 用 Sass 启动 Angular CLI 项目

通常，当我们运行新的 `my-app` 时，我们的应用会有 `.css` 文件。让 CLI 生成 `.scss` 文件（或 `.sass`/`.less`）是一件容易的事。

使用 Sass 创建一个新项目，如下所示：

```ts
ng new my-sassy-app --style=scss
```

## 将当前应用程序转换为 Sass

如果你已经用默认的 `.css` 文件创建了你的 Angular CLI 应用程序，转换它需要更多的工作。您可以使用以下命令告诉 Angular 开始处理 Sass 文件：

```ts
ng set defaults.styleExt scss
```

这将继续，并告诉 Angular CLI 开始处理 `.scss` 文件。如果您想查看这个命令的作用，请查看 Angular CLI 配置文件：`.angular-cli.json`。

您将在文件的底部找到新的配置行：

```ts
"defaults": {
  "styleExt": "scss",
  "component": {
  }
}
```

## 将 CSS 文件更改为 Sass

Angular CLI 现在将开始处理 Sass 文件。然而，它没有经历转换你已经存在的 `.css` 文件到 `.scss` 文件的过程。**您必须手动进行转换**。

## 使用 Sass 导入

我个人喜欢为项目变量和项目混合创建 Sass 文件。这样，我们可以快速轻松地引入任何我们需要的变量/混合。

例如，让我们创建一个全新的 CLI 应用程序：

```ts
ng new my-sassy-app --style=scss
```

接下来，创建以下文件：

```ts
|- src/
    |- sass/
        |- _variables.scss
        |- _mixins.scss
        |- styles.scss
```

为了开始使用这些新的 Sass 文件，我们将把 `_variables.scss` 和 `_mixins.scss` 导入到主 `styles.scss` 中。

```ts
@import './variables';
@import './mixins';
```

最后一步就是更新我们的 `.angular-cli.json` 配置，使用这个新的 `src/sass/styles.scss`，而不是我们原来的 `src/style.scss`。在 `.angular-cli.json` 文件中，只需将下面一行改为指向正确的 `style.scss`。

```ts
"styles": [
  "sass/styles.scss"
],
```

**注意：** 将我们的 Sass 分离到它自己的文件夹中，因为它允许我们创建一个更健壮的 Sass 基础。

现在当我们启动我们的应用程序时，这些新的 Sass 文件将被使用！

## 将 Sass 文件导入 Angular 组件

我们有新的 `_variables.scss` 和 `_mixins.scss` 文件，我们可能想在我们的组件中使用它们。在其他项目中，由于您的 Sass 是由任务运行器编译的，因此您可能习惯于在所有位置访问您的 Sass 变量。

在 Angular CLI 中，所有组件都是独立的，它们的 Sass 文件也是独立的。为了使用组件的 Sass 文件中的变量，您需要导入 `_variables.scss` 文件。

一种方法是使用组件的相对路径 `@import`。如果您有许多嵌套文件夹或最终移动文件，这可能无法扩展。

无论我们在哪个组件 Sass 文件中，我们都可以这样进行导入：

```ts
// src/app/app.component.scss

@import '~sass/variables';

// now we can use those variables!
```

波浪号 (`~`) 将告诉 Sass 在 `src/` 文件夹中查找，并且是导入 Sass 文件的快速快捷方式。

## Sass 包含路径

除了使用 `~`，在使用 CLI 时，我们还可以指定 `includePaths` 配置。要告诉 Sass 查看某些文件夹，请将配置行添加到 `.angular-cli.json`，就像在 `app` 对象旁边的 `styles` 设置一样。

```ts
"styles": [
  "styles.scss"
],
"stylePreprocessorOptions": {
  "includePaths": [
    "../node_modules/bootstrap/scss"
  ]
},
```

## 使用 Bootstrap 文件

我们经常需要做的另一个场景是导入第三方库及其 Sass 文件。

我们将引入 [Bootstrap](https://getbootstrap.com/) ，看看如何将 Sass 文件导入到我们的项目中。这很好，因为我们可以选择我们想要使用 Bootstrap 的哪些部分。我们也可以导入 Bootstrap 混合，并在我们自己的项目中使用它们。

让我们开始，安装 Bootstrap：

```ts
npm install --save bootstrap
```

### 添加 Bootstrap CSS 文件

现在我们有了 Bootstrap，让我们看看如何包含基本的 CSS 文件。通过将 `bootstrap.css` 文件添加到我们的 `.angular-cli.json` 配置：

```ts
"styles": [
  "../node_modules/bootstrap/dist/css/bootstrap.css",
  "sass/styles.scss"
],
```

*注意：* 我们使用 `..` 是因为 CLI 开始从 `src/` 文件夹中查看。我们必须进入一个文件夹才能到达 `node_modules` 文件夹。

虽然我们可以通过这种方式导入 Bootstrap CSS，但是这并不能让我们只导入 Bootstrap 的部分或者使用 Bootstrap 提供的 Sass 变量/混合。

让我们看看如何使用 Bootstrap Sass 文件而不是 CSS 文件。

### 添加 Bootstrap Sass 文件

```ts
@import "functions";
@import "variables";
@import "mixins";
@import "print";
@import "reboot";
@import "type";
@import "images";
@import "code";
@import "grid";
@import "tables";
@import "forms";
@import "buttons";
@import "transitions";
@import "dropdown";
@import "button-group";
@import "input-group";
@import "custom-forms";
@import "nav";
@import "navbar";
@import "card";
@import "breadcrumb";
@import "pagination";
@import "badge";
@import "jumbotron";
@import "alert";
@import "progress";
@import "media";
@import "list-group";
@import "close";
@import "modal";
@import "tooltip";
@import "popover";
@import "carousel";
@import "utilities";
```

这是很多你在自己的项目中可能不会用到的工具。

在我们的 `src/sass/styles.scss` 文件中，让我们只导入我们需要的 Bootstrap 文件。就像我们使用波浪号 (`~`) 从 `src` 文件夹导入 Sass 文件一样，波浪号也会进入 `node_modules` 文件夹。

虽然我们可以使用波浪号，因为我们已经在 `.angular-cli.json` 的 `stylePreprocessorOptions` 部分的 `includePaths` 中添加了 Bootstrap：

```ts
"styles": [
  "styles.scss"
],
"stylePreprocessorOptions": {
  "includePaths": [
    "../node_modules/bootstrap/scss"
  ]
},
```

我们可以执行以下操作来仅获取 Bootstrap 库工具：

```ts
@import 
  'functions',
  'variables',
  'mixins',
  'print',
  'reboot',
  'type';
```

**参考：** https://scotch.io/tutorials/using-sass-with-the-angular-cli