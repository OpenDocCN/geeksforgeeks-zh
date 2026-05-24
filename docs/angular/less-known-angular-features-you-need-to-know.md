# 你需要知道的不太为人知的角度特征

> 原文:[https://www . geeksforgeeks . org/鲜为人知的角度特征-你需要知道的/](https://www.geeksforgeeks.org/less-known-angular-features-you-need-to-know/)

以下是 angular 的一些有趣的特性，可以帮助您进行搜索引擎优化、提高应用程序性能和提高代码可读性。

**1。标题标签:**显示在搜索引擎结果页面上，作为搜索文本的可点击&可触摸标题。它们对于可用性、搜索引擎优化和社交平台帖子分享非常重要。

为此，您必须从*@ angular/platform-browser*包中导入 ***标题*** ，并将其注入构造器。这样，您还可以动态设置文本。

**示例:**

## java 描述语言

```ts
import { Title } from "@angular/platform-browser"
@Component({
  //..
  //..
  //..
})
export class LoginComponent implements OnInit {
  constructor(private title: Title) { }
  ngOnInit() {
    title.setTitle("Login")
  }
}
```

**2。元标签:**正如我们所知，元标签对于网站的索引很重要，可以让它很容易在互联网上被发现。您可以使用*添加标签*方法添加这些标签。

为此首先，您必须从*@ angular/platform-browser*包导入元属性，并将其注入构造函数。这样，您就可以添加、更新、删除元标签属性。

**示例:**

## java 描述语言

```ts
import { Meta, Title } from '@angular/platform-browser';

constructor(meta: Meta) {
  meta.addTag({ name: 'description', 
    content: 'sample content of meta service' });
  const authorName = meta.getTag('name=author');
  console.log(authorName.content);
  meta.updateTag({
    name: 'twitter:description', content: sample description' 
  });
  meta.removeTag('name="author"');
}
```

**输出:**这将呈现如下:

```ts
<meta name="twitter:title" content="Your Website Title" />
```

这些都是推特的社交元标签。

**3。模板插值:**角度还可以覆盖插值括号。正如我们所知，默认情况下，模板插值器在我们的模板中是**{ } }**。它用于显示组件中的字段(属性)。

**示例:**

## java 描述语言

```ts
@Component({
  interpolation: ["((", "))"]
})

export class AppComponent { }

// Here we override this { } to ().
<hello name="{{ name }}"></hello>
```

**输出:**这将呈现如下:

```ts
<hello name="(( name ))"></hello>
```

**4。位置服务:**有了这个，可以从当前浏览器窗口的地址栏获取链接。使用起来很简单，只需要从 *@angular/common* 包导入 Location，并注入到构造器中即可。

**示例:**

## java 描述语言

```ts
import { Location } from "@angular/common"

@Component({
  //...
  //...
})

export class AppComponent {
  constructor(private location: Location) { }
  navigateTo(url) {
    this.location.go(url)
  }
  goBack() {
    location.back()
  }
  goForward() {
    location.forward()
  }
}
```

**5。JS 的文档属性:**如果要使用文档方法，那么首先需要使用 inject decorator 将其注入到构造函数中。最好不要直接操作 DOM 元素。如果你直接这样做，它会给 XSS 带来机会。

**示例:**

## java 描述语言

```ts
import { DOCUMENT } from '@angular/common';
import { Component, Inject, VERSION } from '@angular/core';

constructor(@Inject(DOCUMENT) _doc: Document) {
  console.log(_doc)
}

renderCanvasElement() {
  this._doc.getElementById("canvas")
}
```

**6。属性装饰器**它基本上是用来提高应用程序的性能。正如我们所知，输入发射器将在每个影响性能的变化检测中运行。因此，如果您想传递一些数据或字符串，您可以使用属性装饰器。它会检查属性一次。

**示例:**

## java 描述语言

```ts
import { Component, Attribute, Input } from '@angular/core';
@Component({
  selector: 'my-app',
  template: `<hello type="some string type"></hello>`,
})

export class AppComponent { }

@Component({
  selector: 'hello',
  template: `<h1>Hello</h1> Type: "{{myVar}}"`,
  styles: [`h1 { font-family: Lato; }`]
})

export class HelloComponent {
  constructor(@Attribute('type') public myVar: string) {
    console.log('Attributre =', myVar);
  }
}
```

**7。App Initialzer 令牌:**当我们需要在加载我们的应用程序之前进行一些初始化时使用，例如添加配置、加载缓存、管理设置或进行一些签入。

**示例:**

## java 描述语言

```ts
import { APP_INITIALIZER } from '@angular/core';

function runSettingsOnInit() {
  // ...
}

@NgModule({
  providers: [
    { provide: APP_INITIALIZER, useFactory: runSettingsOnInit }
  ]
})
```

**8。应用引导监听器:**它使我们能够监听组件何时被引导。将此添加到应用程序模块中的*模块*装饰器的提供商中。

**示例:**

```ts
import { APP_BOOTSTRAP_LISTENER } from '@angular/core';
@NgModule({
 {
  provide: APP_BOOTSTRAP_LISTENER, multi: true,
  useExisting: runOnBootstrap 
 }
 // ...
})
```