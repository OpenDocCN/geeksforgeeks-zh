# Vue 3 有什么新功能？

> 原文:[https://www.geeksforgeeks.org/whats-new-in-vue-3/](https://www.geeksforgeeks.org/whats-new-in-vue-3/)

[Vue](https://www.geeksforgeeks.org/vue-js-introduction-installation/) 是一个**渐进式 Javascript 框架**用于构建 UI 和单页应用。这是一个开源的**模型-视图-视图模型(MVVM)** 框架。核心框架主要集中在视图层，它可以很容易地与其他库和项目集成。使用现代工具和支持库，单页应用程序可以轻松处理。

**Vue 3:** 作为一名 JavaScript 开发人员，Vue 3 将成为现代 web 开发领域的里程碑。Vue.js 3.0 于 7 月 22 日作为 Release 候选者发布，并带来了许多令人兴奋的新特性。现在 API 和实现都很稳定。很快就会正式发布。

Vue 3 是更小、更快、更易维护，配备更好的 TypeScript 支持，更容易针对原生。

**功能:**Vue 3 的一些新功能使其使用更加方便，这些新功能有:

性能增强

成分原料药

门户

多根组件

打字稿

**性能提升:**

*   **smaller:** Vue3 is smaller. It is tree shaking-friendly, which means that it only allows to import fragments of the required library and deletes unnecessary code. The kernel runtime has been reduced to 12kb.
*   **Faster:** Vue3 is faster. The virtual Document Object Model has been rewritten from the beginning with the new differencing algorithm to make it faster to install, repair and render.

**成分 API:** 它是 Vue 3 中最伟大的特性之一。组合应用编程接口在 Vue2 中作为插件提供，但它将在 Vue 3 中被烘焙。目前，我们使用选项应用编程接口构建组件，这使得大型组件难以维护和管理。

根据 Vue 核心团队的说法，Composition API 是*“*一组可添加的、基于功能的 API，允许灵活地组合组件逻辑*“*”。它允许更好地组织和重用代码。

**传送门:**瞬移或传送门是一个新功能，允许我们在不同的 DOM 树中将代码的一部分从一个组件渲染到另一个组件。这是 React 中已经实现的特性之一。使用门户，我们可以轻松地处理出现在页面顶部的模式、弹出窗口和组件。我们可以从 z-index 的糟糕使用中得到缓解，我们使用它来避免 CSS 覆盖主机组件。

门户功能在 Vue 2 中以第三方库的形式出现，但现在它将作为一个内置功能出现，并且可以通过使用标签<teleport>来使用</teleport>

**多根组件:**到目前为止，Vue 模板可以有一个标签，即一个根元素。即使我们想要两个< p >标签作为同级标签，我们也必须将它们包含在一个< div >标签中。但是，在 Vue 3 中，这个限制被取消了，没有必要使用根元素。我们现在可以在<模板>标签中使用任意多的兄弟标签。

**TypeScript:** Vue 在 2.0 版本后期开始支持 TypeScript，在 Vue 3 中也继续支持。Vue 3 的源代码完全是用 TypeScript 编写的，因此组合 API 得到了增强的支持。但是，它也是可选的。

除了所有这些主要功能，Vue 3 还涵盖了许多较小的改进。许多作为第三方库可用的特性现在都包含在 Vue 3 框架的核心中。它充满了许多令人惊叹的新功能。有了所有这些有趣的特性，性能得到了微调，开发人员的体验变得越来越简单。