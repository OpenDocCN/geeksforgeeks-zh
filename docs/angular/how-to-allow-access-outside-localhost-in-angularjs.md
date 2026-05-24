# 如何在 AngularJS 中允许本地主机以外的访问？

> 原文:[https://www . geesforgeks . org/如何允许访问-外部-localhost-in-angularjs/](https://www.geeksforgeeks.org/how-to-allow-access-outside-localhost-in-angularjs/)

首先，让我们讨论如何构建一个 Angular 应用程序，运行它，并在浏览器中预览它。我们可以使用 Angular 提供的命令行界面轻松完成。命令行界面是一种命令行界面工具，通过使用它，开发人员在初始化应用程序、开发应用程序、搭建和高效维护应用程序时面临的挑战更少。在 Angular 中开发应用程序并不总是需要 CLI，但它肯定会给开发人员提供一个高质量的工具集，使代码更令人印象深刻，并节省时间。

**CLI 上的亮点:**

*   创建新的角度应用程序。
*   运行一个支持 LiveReload 的开发服务器，在开发过程中预览你的应用程序。
*   向现有的“角度”应用程序添加不同的特征。
*   运行应用程序的单元测试。
*   运行应用程序的端到端(E2E)测试。
*   构建应用程序以部署到生产中。

让我们构建第一个 Angular 应用程序。一些先决条件如下:

1.  Node.js 6.9.0
2.  npm 3.0.0 或更高版本

**安装:**要安装 Angular CLI，请在命令提示符下运行以下命令，这将在您的系统中安装 ng。

```ts
$ npm install -g @angular/cli 
```

为了检查版本，我们将编写以下命令-

```ts
$ ng version 
```

这将给出您已安装的版本。

```ts
@angular/cli: 1.0.0
node: 6.10.0
os: darwin x64
```

**新应用程序的创建:**要在开发服务器上构建和服务新的 Angular 项目，请转到新工作区的父目录，并使用以下命令:

```ts
$ ng new my-first-Angular-application 
```

这个新命令将在当前的工作目录下创建一个新的文件夹，新的 Angular 应用程序的所有源文件和目录都是根据您指定的名称“我的第一个 Angular 应用程序”创建的。npm 依赖项已安装。请注意，您想要创建的所有文件都可以在文件夹中创建。如果当前工作目录不适合您的项目，您可以通过运行 cd 将其更改为另一个目录。

要在浏览器中预览新应用程序，请导航到其目录:

```ts
$ cd my-first-Angular-application
```

然后运行:

```ts
$ ng serve
```

在浏览器中，打开*<u>http://localhost:4200/</u>*查看我的-first-Angular-application 的结果。当您使用 ng serve 命令构建应用程序并在本地提供服务时，服务器会自动重建应用程序，并在您更改任何源文件时重新加载页面。创建、构建和运行您的 Angular 应用程序就这么简单。

**现在主要问题出现了，为什么我们需要允许从外部访问 localhost？**
答案是，作为开发人员，我们经常使用不止一台设备或计算机来根据我们的需求运行我们的应用程序。这将使我们的工作有效率，而且我们可以节省很多时间。为了允许从外部访问 localhost，我们对前面看到的 ng serve 注释进行了简单的修改。

```ts
$ ng serve --host 0.0.0.0
```

然后键入 192.168.x.x:4200 以从另一台机器访问。x.x 代表您的 IP 地址的最后两个带点的十进制数字。或者你可以简单地输入-

```ts
$ ng serve --host 192.168.X.X
```

如果您仍然无法访问 192.168.X.X:4200，您可能处于防火墙保护打开的网络中。禁用保护并再次检查。

[角度 CLI |角度项目设置](https://www.geeksforgeeks.org/angular-cli-angular-project-setup/)