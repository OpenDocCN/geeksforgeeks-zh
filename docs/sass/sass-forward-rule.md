# SASS | @转发规则

> 原文:[https://www.geeksforgeeks.org/sass-forward-rule/](https://www.geeksforgeeks.org/sass-forward-rule/)

**@forward 规则**处理 Sass 样式表，并在使用@use 规则加载样式表的情况下使它们的函数、混合和变量可用。跨许多文件组织 Sass 库成为可能，同时为用户提供处理单个入口点文件的能力。

**语法:**

```html
@forward "<url>"
```

上面的代码加载了给定网址上可用的模块。它使加载模块的公共成员对模块的用户可用，就像它们是直接在模块中定义的一样。如果需要，这些成员在模块中不可用，也可能使用 **@use** 规则。它只处理模块一次。如果**@前进**和**@使用**都是为同一个文件中的同一个模块编写的，那么总是先写**@前进**。通过这种方式，如果用户想要配置转发模块，该配置将在@use 处理它之前应用于@forward，而无需任何配置。
**示例:**

```html
// gfg/_list.css
@mixin geeks 
  font-family: times new roman
  font-size: 4px
  padding: 2px

// geeksforgeeks.scss
@forward "gfg/list"

// style.scss
@use "geeksforgeeks"
gfg1 
  @include geeksforgeeks.geeks
```

这将导致以下 CSS 输出:

```html
gfg1 {
  font-family: times new roman
  font-size: 4px
  padding: 2px
}

```

**添加前缀:**
有时，名称在定义它们的模块之外可能不正确，因此，@forward 可以选择为它所指向的所有成员添加额外的前缀。
**语法:**

```html
@forward "<url>" as <prefix>-*
```

这会将给定的前缀添加到模块指向的每个 mixin、函数和变量名的开头。
**例:**

```html
// gfg/_list.css
@mixin forgeeks
  font-family: times new roman
  font-size: 4px
  padding: 2px

// geeks.scss
@forward "gfg/list" as geeks*

// style.scss
@use "geeksforgeeks"
gfg1 
  @include geeks.geeksforgeeks
```

这将导致以下 CSS 输出:

```html
gfg1 {
  font-family: times new roman
  font-size: 4px
  padding: 2px
}

```

**配置模块:**
使用@forward 规则也可以处理具有配置的模块。@转发规则的配置也可以用！其配置中的默认标志。这允许模块更改上游样式表的默认值，同时也允许下游样式表覆盖它们。
**例:**

```html
// _gfg.sass
$green: #000 !default
$border-radius: 2px !default
$box-shadow: 0 2px 1px rgba($green, 1) !default

geeks
  border-radius: $border-radius
  box-shadow: $box-shadow

// _geeksforgeeks.sass
@forward 'gfg' with ($green: #222 !default,
               $border-radius: 4px !default)

// style.sass
@use 'geeksforgeeks' with ($green: #333)
```

这将导致以下 CSS 输出:

```html
geeks {
  border-radius: 4px;
  box-shadow: 0 2px 1px rgba(51, 51, 51, 1);
}

```