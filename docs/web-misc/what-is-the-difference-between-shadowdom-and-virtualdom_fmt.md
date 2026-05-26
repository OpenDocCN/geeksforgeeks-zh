# ShadowDOM 和 VirtualDOM 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-shadowdom-and-virtualdom/](https://www.geeksforgeeks.org/what-is-the-difference-between-shadowdom-and-virtualdom/)

[`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 是客户端开发中遵循的一个流行概念。这是一种跨平台且独立于语言的基本技术。它被定义为通过对象创建逻辑结构化文档的 [`HTML`](https://www.geeksforgeks.org/html-tutorials/) 或 [`XML`](https://www.geeksforgeks.org/xml-tutorial/) 文档的应用编程接口。

## 虚拟 DOM

*   [`Virtual DOM`](https://www.geeksforgeks.org/introduction-to-virtual-dom/)，简单来说，是真实 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的一个完整且全面的表示。
*   因为对 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的任何更改都会导致页面更频繁地渲染，[`Virtual DOM`](https://www.geeksforgeks.org/introduction-to-virtual-dom/) 主要试图避免对 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 进行任何不必要且昂贵的更改。
*   这是通过将更改分组并进行单次重新渲染来实现的，而不是进行多次小的重新渲染。
*   [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的一个副本存储在内存中，用于比较 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 中任何正在发生的变化，并通过比较找出差异。因此，只有应用程序的更新部分被重新渲染，而不是整个 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/)。
*   [`VueJS`](https://www.geeksforgeks.org/vue-js-introduction-installation/) 和 [`ReactJS`](https://www.geeksforgeks.org/react-js-introduction/) 都使用 [`Virtual DOM`](https://www.geeksforgeks.org/introduction-to-virtual-dom/)。

## 影子 DOM

*   [`Shadow DOM`](https://www.geeksforgeks.org/shadow-dom-in-html/) 主要与封装的概念相关。它是一个允许开发者克服 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 封装的工具。
*   这意味着浏览器有能力在文档的渲染中添加一个 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 元素的子树，但它不会被添加到主文档的 [`DOM树`](https://www.geeksforgeks.org/introduction-to-dom/) 中。
*   因此，它隔离了 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/)，并确保组件的 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 是一个独立的元素，不会出现在全局 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 中。
*   与 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 相比，[`Shadow DOM`](https://www.geeksforgeks.org/shadow-dom-in-html/) 以较小的块出现，这意味着（与 [`Virtual DOM`](https://www.geeksforgeks.org/introduction-to-virtual-dom/) 不同）它不是整个 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的完整表示。
*   它也被证明对 [`CSS`](https://www.geeksforgeks.org/css-tutorials/) 作用域有帮助。应用程序中使用的样式可能会重叠，这使得处理它们变得很麻烦。[`Shadow DOM`](https://www.geeksforgeks.org/shadow-dom-in-html/) 确保在单个 [`Shadow DOM`](https://www.geeksforgeks.org/shadow-dom-in-html/) 元素中创建的样式保持隔离并在其自己的作用域内。

### Shadow DOM 和 Virtual DOM 的区别

| 虚拟 DOM | 影子 DOM |
| --- | --- |
| 它围绕着解决性能问题。 | 它围绕着封装的概念。 |
| 它是一个实际 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的完整表示。 | 它不是整个 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 的完整表示。 |
| 它将几个变化组合在一起，进行一次重新渲染，而不是多次小的变化。 | 它将 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 元素的子树添加到文档的渲染中，而不是将其添加到主文档的 [`DOM树`](https://www.geeksforgeks.org/introduction-to-dom/) 中。 |
| 它创建了整个 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 对象的副本。 | 它创建了 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/) 对象的小块，它们有自己独立的范围。 |
| 它不孤立 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/)。 | 隔离 [`DOM`](https://www.geeksforgeks.org/dom-document-object-model/)。 |
| 这对 [`CSS`](https://www.geeksforgeks.org/css-tutorials/) 范围界定没有帮助。 | 有助于 [`CSS`](https://www.geeksforgeks.org/css-tutorials/) 的范围界定。 |