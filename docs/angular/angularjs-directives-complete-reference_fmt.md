# AngularJS 指令完整参考

> 原文:[https://www . geeksforgeeks . org/angular js-指令-完整-参考/](https://www.geeksforgeeks.org/angularjs-directives-complete-reference/)

![](img/4dfe222d971b935a65fd89aa27f2c8e4.png)

指令是文档对象模型(DOM)中的标记。指令可以与任何控制器或 HTML 标记一起使用，这些标记将告诉编译器预期的确切操作或行为。存在一些预定义的指令，但是如果开发人员需要，他可以创建新的指令(自定义指令)。

**示例:** 本示例使用 `ng-app` 指令定义默认 AngularJS 应用程序。

```ts
<html>        
<head> 
    <title>AngularJS ng-app Directive</title> 
    <script src= 
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
    </script> 
</head> 
<body style="text-align:center">

<h2 style = "color:green">ng-app directive</h2> 
    <div ng-app="" ng-init="name='GeeksforGeeks'"> 
        <p>{{ name }} is the portal for geeks.</p>
    </div> 
</body>   
</html> 
```

**输出:**

![](img/70c5d3fcbddee0ea74fbf1a0aa8f419a.png)

下表列出了重要的内置 AngularJS 指令。

| 指令 | 描述 |
| --- | --- |
| `ng-app` | AngularJS 应用程序的开始。 |
| `ng-init` | 用于初始化变量 |
| `ng-model` | `ng-model` 用于绑定到 HTML 控件 |
| `ng-controller` | 将控制器附着到视图 |
| `ng-bind` | 将该值与 HTML 元素绑定 |
| `ng-repeat` | 对指定集合中的每个项目重复一次 HTML 模板。 |
| `ng-show` | 显示或隐藏关联的 HTML 元素 |
| `ng-readonly` | 将 HTML 元素设为只读 |
| `ng-disabled` | 用于动态禁用或启用按钮 |
| `ng-if` | 移除或重新创建 HTML 元素 |
| `ng-click` | 点击自定义步骤 |

**指令:**

*   [AngularJS | `ng-app` 指令](https://www.geeksforgeeks.org/angularjs-ng-app-directive/)
*   [AngularJS | `ng-href` 指令](https://www.geeksforgeeks.org/angularjs-ng-href-directive/)
*   [AngularJS | `ng-required` 指令](https://www.geeksforgeeks.org/angularjs-ng-required-directive/)
*   [AngularJS | `ng-init` 指令](https://www.geeksforgeeks.org/angularjs-ng-init-directive/)
*   [AngularJS | `ng-paste` 指令](https://www.geeksforgeeks.org/angularjs-ng-paste-directive/)
*   [AngularJS | `ng-open` 指令](https://www.geeksforgeeks.org/angularjs-ng-open-directive/)
*   [AngularJS | `ng-options` 指令](https://www.geeksforgeeks.org/angularjs-ng-options-directive/)
*   [AngularJS | `ng-selected` 指令](https://www.geeksforgeeks.org/angularjs-ng-selected-directive/)
*   [AngularJS | `ng-non-bindable` 指令](https://www.geeksforgeeks.org/angularjs-ng-non-bindable-directive/)
*   [AngularJS | `ng-list` 指令](https://www.geeksforgeeks.org/angularjs-ng-list-directive/)
*   [AngularJS | `ng-disabled` 指令](https://www.geeksforgeeks.org/angularjs-ng-disabled-directive/)
*   [AngularJS | `ng-mouseup` 指令](https://www.geeksforgeeks.org/angularjs-ng-mouseup-directive/)
*   [AngularJS | `ng-keyup` 指令](https://www.geeksforgeeks.org/angularjs-ng-keyup-directive/)
*   [AngularJS | `ng-focus` 指令](https://www.geeksforgeeks.org/angularjs-ng-focus-directive/)
*   [AngularJS | `ng-keypress` 指令](https://www.geeksforgeeks.org/angularjs-ng-keypress-directive/)
*   [AngularJS | `ng-hide` 指令](https://www.geeksforgeeks.org/angularjs-ng-hide-directive/)
*   [AngularJS | `ng-dblclick` 指令](https://www.geeksforgeeks.org/angularjs-ng-dblclick-directive/)
*   [AngularJS | `ng-mousedown` 指令](https://www.geeksforgeeks.org/angularjs-ng-mousedown-directive/)
*   [AngularJS | `ng-change` 指令](https://www.geeksforgeeks.org/angularjs-ng-change-directive/)
*   [AngularJS | `ng-maxlength` 指令](https://www.geeksforgeeks.org/angularjs-ng-maxlength-directive/)
*   [AngularJS | `ng-blur` 指令](https://www.geeksforgeeks.org/angularjs-ng-blur-directive/)
*   [AngularJS | `ng-controller` 指令](https://www.geeksforgeeks.org/angularjs-ng-controller-directive/)
*   [AngularJS | `ng-mouseleave` 指令](https://www.geeksforgeeks.org/angularjs-ng-mouseleave-directive/)
*   [AngularJS | `ng-bind` 指令](https://www.geeksforgeeks.org/angularjs-ng-bind-directive/)
*   [AngularJS | `ng-mouseenter` 指令](https://www.geeksforgeeks.org/angularjs-ng-mouseenter-directive/)
*   [AngularJS | `ng-click` 指令](https://www.geeksforgeeks.org/angularjs-ng-click-directive/)
*   [AngularJS | `ng-copy` 指令](https://www.geeksforgeeks.org/angularjs-ng-copy-directive/)
*   [AngularJS | `ng-mousemove` 指令](https://www.geeksforgeeks.org/angularjs-ng-mousemove-directive/)
*   [AngularJS | `ng-minlength` 指令](https://www.geeksforgeeks.org/angularjs-ng-minlength-directive/)
*   [AngularJS | `ng-checked` 指令](https://www.geeksforgeeks.org/angularjs-ng-checked-directive/)
*   [AngularJS | `ng-if` 指令](https://www.geeksforgeeks.org/angularjs-ng-if-directive/)
*   [AngularJS | `ng-cut` 指令](https://www.geeksforgeeks.org/angularjs-ng-cut-directive/)
*   [AngularJS | `ng-readonly` 指令](https://www.geeksforgeeks.org/angularjs-ng-readonly-directive/)
*   [AngularJS | `textarea` 指令](https://www.geeksforgeeks.org/angularjs-textarea-directive/)
*   [AngularJS | `input` 指令](https://www.geeksforgeeks.org/angularjs-input-directive/)
*   [AngularJS | `ng-include` 指令](https://www.geeksforgeeks.org/angularjs-ng-include-directive/)
*   [AngularJS | `ng-jq` 指令](https://www.geeksforgeeks.org/angularjs-ng-jq-directive/)
*   [AngularJS | `ng-model` 指令](https://www.geeksforgeeks.org/angularjs-ng-model-directive/)
*   [AngularJS | `ng-transclude` 指令](https://www.geeksforgeeks.org/angularjs-ng-transclude-directive/)
*   [AngularJS | `ng-class-even` 指令](https://www.geeksforgeeks.org/angularjs-ng-class-even-directive/)
*   [AngularJS | `ng-class-odd` 指令](https://www.geeksforgeeks.org/angularjs-ng-class-odd-directive/)
*   [AngularJS | `ng-value` 指令](https://www.geeksforgeeks.org/angularjs-ng-value-directive/)
*   [AngularJS | `ng-bind-template` 指令](https://www.geeksforgeeks.org/angularjs-ng-bind-template-directive/)
*   [AngularJS | `ng-form` 指令](https://www.geeksforgeeks.org/angularjs-ng-form-directive/)
*   [AngularJS | `ng-bind-html` 指令](https://www.geeksforgeeks.org/angularjs-ng-bind-html-directive/)
*   [AngularJS | `ng-class` 指令](https://www.geeksforgeeks.org/angularjs-ng-class-directive/)
*   [AngularJS | `ng-pluralize` 指令](https://www.geeksforgeeks.org/angularjs-ng-pluralize-directive/)
*   [AngularJS | `ng-pattern` 指令](https://www.geeksforgeeks.org/angularjs-ng-pattern-directive/)
*   [AngularJS | `ng-style` 指令](https://www.geeksforgeeks.org/angularjs-ng-style-directive/)
*   [AngularJS | `ng-switch` 指令](https://www.geeksforgeeks.org/angularjs-ng-switch-directive/)
*   [AngularJS | `ng-show` 指令](https://www.geeksforgeeks.org/angularjs-ng-show-directive/)
*   [AngularJS | `ng-srcset` 指令](https://www.geeksforgeeks.org/angularjs-ng-srcset-directive/)
*   [AngularJS | `ng-src` 指令](https://www.geeksforgeeks.org/angularjs-ng-src-directive/)
*   [AngularJS | `ng-submit` 指令](https://www.geeksforgeeks.org/angularjs-ng-submit-directive/)