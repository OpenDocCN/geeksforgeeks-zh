# Bootstrap 3 与 Bootstrap 4 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-bootstrap-3-and-bootstrap-4/](https://www.geeksforgeeks.org/difference-between-bootstrap-3-and-bootstrap-4/)

**Bootstrap:** Bootstrap 由 Mark Otto 和 Jacob Thorton 于 2011 年 8 月在 Twitter 上开发。这是一个开源框架，用于更快更容易地设计响应性网站。它是最流行的开源框架，包括 HTML、CSS 和 JavaScript。它可以使用任何服务器端技术（如 Java、PHP 等）创建网络应用程序，其响应设计允许任何平台（如平板电脑和移动设备）运行。

我们使用 Bootstrap 有很多原因，包括：
*   Response design
*   Browser support
*   Mobile first style
*   Yi Xue

**不同版本的 Bootstrap:**
*   **Version 2.0** supports responsive web page design.
*   **Version 3.0** supports mobile priority design.
*   **Version 4.0** introduces SASS and Flexbox support.

## Bootstrap 3 与 Bootstrap 4 的区别

| **Basic off** | **Bootstrap 3** | **Bootstrap 4** |
| :--- | :--- | :--- |
| **Grid system** | It is based on a four-tier grid system (`xs`, `sm`, `md`, `lg`). | Based on 5-tier grid system (`xs`, `sm`, `md`, `lg`, `xl`). |
| **CSS file** | Less | Sass |
| **Button size** | `.btn-xs` class is supported. | In which you are unique. `.btn-sm` and `.btn-lg` is available. |
| **Horizontal** | `.row` classes are not required when using grids in forms. | `.row` classes are required when using grids in forms. |
| **Inverse table** | No support. | In which we can add an inverse table. `.table-inverse` class. |
| **Primary unit** | Pixel | Rem |
| **font size** | 16px | |
| **Responsive table** | The response table class is added to the `<div>` element. | In bootstrap 4, `.table-responsive` use the element to add the response table class. |
| **Concentration table** | It supports. `.table-condensed`. | It supports. `.table-sm` |
| **Responsive image** | Use. `.img-responsive` class. | `.img-fluid` grade. |
| **Image alignment** | Use. `.pull-right` and `.pull-left` class. | Can be used. `.float-right`, `.float-left` and various other classes. `.text-left` and `.text-right`, `.text-center`. |
| **Structure** | For the application drop-down list, we use `<ul>` and `<li>`. | Apply. We use `<a>` and `<div>` for the drop-down items. |
| **color** | Limited colors are available. It supports `.navbar-inverse` but does not support other classes. | There are many colors to choose from. `.bg-*` or `.navbar-light`, `.navbar-dark` class. |
| **redundant screen** | `.container-fluid` type is required for the whole web. | `.container-fluid` for large screens and `.jumbotron-fluid` for full-width jumbotrons. |
| **Label pill** | `.label` pills are not available. | `.badge-pill` for round corners. |
| **pager** | It uses `.next` or `.previous`. | In which we use `.page-next` or `.page-previous`. |
| **Class** | Use. The bread crumbs are labeled with `<ul>`. | `.breadcrumb` are next to the `<li>` label. |
| **Affleck** | be | no |
| **Flexbox** | be | |
| **Turntable Project** | It uses. `.carousel-project` classes. | |
| **dividing line** | Applicable. The `.divider` class is `<li>` element. | `.dropdown-divider` the dividing line class to the `<div>` element. |