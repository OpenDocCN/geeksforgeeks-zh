# 角度的微小变化

> 原文:[https://www . geeksforgeeks . org/mini % ef % AC % 81 in-angular/](https://www.geeksforgeeks.org/mini%ef%ac%81cation-in-angular/)

任何应用的性能都是决定这个世界用户体验的关键因素之一。如果性能低下，应用程序将无法实现其对用户的真正价值。因此，为了在生产环境中获得更好的性能，我们鼓励在编码过程中采用各种实践。
同样，Angular 框架也提供了各种选项，以在运行时实现更高的性能。其中一些是 AOT 编译，捆绑，缩小等。在 **AOT 编译**中，Angular 编译器在应用程序部署之前运行，因此减少了应用程序的整体大小。但是默认情况下，Angular 框架不会发生这种情况。

现在，让我们来谈谈 Angular 框架采用的默认流程，它帮助开发人员实现更高的性能，即捆绑和缩小。让我们在下面详细讨论它们:

**捆绑和缩小**是 Angular 采用的两个重要过程，目的是缩小应用程序的大小，以便在浏览器中快速下载。

**捆绑:**

*   在捆绑中，应用程序中的所有 js 文件都作为一个单元下载，而不是下载每个 js 文件，这总体上减少了应用程序下载的总时间，从而实现了更高的性能。
*   让我们举个例子来理解它:
    *假设我的应用程序中有三个 js 文件。因此，当部署应用程序时，默认情况下，Angular 框架将所有这三个 js 文件合并到一个文件中，从而减小了应用程序的大小，现在它可以在用户浏览器中快速下载。*

**缩小:**在缩小过程中，在 js 文件中执行以下操作，以减小 js 文件的大小，从而加快下载速度。

*   它会删除文件中的所有空格。
*   它删除文件中所有不需要的变量。
*   它将所有大的变量名转换成小的变量名。

通过做所有这些事情，Angular 框架减少了 js 文件的整体大小。此外，Angular 框架还增加了。最小到文件名，表示该特定文件的缩小。

让我们举个例子来更好地理解缩小过程。

**module.js:**

## java 描述语言

```ts
module.exports = function(module) {
    if (!module.webpackPolyfill) {
        module.deprecate = function() {};
        module.paths = [];

        // module.parent = undefined by default
        if (!module.children) module.children = [];
        Object.defineProperty(module, "loaded", {
            enumerable: true,
            get: function() {
                return module.l;
            }
        });
        Object.defineProperty(module, "id", {
            enumerable: true,
            get: function() {
                return module.i;
            }
        });
        module.webpackPolyfill = 1;
    }
    return module;
};
```

运行**ng build–prod**时，Angular 框架简化的代码是:

**module.min.js:**

## java 描述语言

```ts
module.exports=function(e){return e.webpackPolyfill||(e.deprecate=function(){},e.paths=[],e.children||(e.children=[]),Object.defineProperty(e,"loaded",{enumerable:!0,get:function(){return e.l}}),Object.defineProperty(e,"id",{enumerable:!0,get:function(){return e.i}}),e.webpackPolyfill=1),e};
```

所以，正如你在缩小的版本中看到的，所有的空格都被去掉了，变量名被缩短了。因此，将代码减少到只有一行代码会减少 js 文件和应用程序的整体大小。

因此，缩小和捆绑实际上是相互关联的过程，有助于减小 js 文件的大小，以便在浏览器中更快地下载，并给用户带来愉快的体验。在提高应用程序的整体性能方面，这些是 Angular 框架的基本支柱。