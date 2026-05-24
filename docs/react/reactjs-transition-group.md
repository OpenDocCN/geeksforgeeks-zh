# 反应|过渡组

> 原文:[https://www.geeksforgeeks.org/reactjs-transition-group/](https://www.geeksforgeeks.org/reactjs-transition-group/)

虽然 React 管理不同的组件及其行为以使任何网络应用程序具有交互性，但它不包含为应用程序本身增加美感的方法。动画被认为是为应用程序增加美感的最常用方法之一，我们可以使用一组称为**反应过渡组**的显式组件为反应应用程序添加动画。

过渡小组的开发人员将其定义为:

> 一组组件，用于管理一段时间内的组件状态(包括装载和卸载)，专门针对动画设计。

您可以通过使用反应过渡组来改进用户界面:

*   在你的机器上应该安装节点版本> =6
*   npm 必须安装在您的计算机上。

您可以使用以下命令在项目组件中安装过渡组:

```jsx
npm install react-transition-group --save
```

您可以使用以下命令在项目组件中导入过渡组件:

```jsx
import { Transition } from 'react-transition-group';
```

在实施过渡小组之前，我们必须考虑以下几个要点。

**注意要点:**

*   我们可以使用 React Transition 组实现的动画是纯 **CSS Transitions** ，也就是说，它没有使用 JavaScript 的任何属性来制作组件的动画。动画是通过用不同的 CSS 样式定义类，并在组件生命周期的指定点装备和不装备类来完成的。
*   React 本来是用来创建网络应用程序的，开发人员认为最好将动画等其他附加功能分开，以保持 react 的轻量级。因此，为了使用过渡组，我们需要单独安装它，这将在本文的后面介绍。
*   React Transition 组由三个主要组件组成 **Transition** 、 **CSSTransition** 和 **TransitionGroup** 我们将在本文后面简要介绍其中的每一个组件，由于其受欢迎程度，我们将实现 CSSTransition 组件。
*   反应过渡组仅由组件组成，即为了实现任何组件或 HTML 元素的动画，我们必须首先将它们包装在三个现有组件中的任何一个中。
*   最后，让我们了解过渡小组是如何工作的。React Transition Group 组件将任何其他子组件的生命周期划分为特定的阶段，开发人员可以选择在这些阶段中添加特定的类，时间跨度称为**超时**。这就是 JavaScript 的使用结束的地方。现在只剩下开发人员给类赋予不同的风格，并为动画添加 CSS Transitions。

**反应过渡族组分:**

如前所述，反应过渡组由三个主要组件组成**过渡**、**过渡**和**过渡组**。现在让我们简要描述以下内容。

*   **Transition**:Transition 组件有一个简单的 API，允许开发人员描述一段时间内从一个组件状态到另一个组件状态的转换。它主要用于制作组件安装和卸载的动画，但也可用于创建更复杂的动画。
    根据过渡部分，过渡可分为四个主要阶段:
    *   进入
    *   进入
    *   令人兴奋的
    *   激动的
*   **CSSTransition** :顾名思义这个过渡组件依赖于 CSS 的过渡和动画。它的灵感来自于 [ng 动画](http://www.nganimate.org/)库。根据转换组件，转换可以分为三个主要阶段:
    *   出现
    *   进入
    *   出口
*   **TransitionGroup**:Transition group 组件用于管理列表中的一组 Transition 组件，类似于 Transition 组件本身，Transition group 不直接设置动画，它是一个状态机，因为它跟踪组件的当前状态，即安装或卸载。
    TransitionGroup 组件主要用于在一个组件中有不同的动画，这可以通过在 Transition group 组件中包装几个 Transition 组件来实现。转换组可以包含任何可用的组件。关于 TransitionGroup 组件的更多信息将在以后的文章中讨论。

*   现在，我们已经了解了什么是反应过渡组以及它的组成部分。我们应该对每个组件进行分析，并结合几个例子详细了解它们。最后，我们将创建一个非常简单的应用程序来总结我们学到的东西。

**参考文献:**

*   [https://github.com/reactjs/react-transition-group](https://github.com/reactjs/react-transition-group)
*   [https://reactcommunity.org/react-transition-group/](https://reactcommunity.org/react-transition-group/)