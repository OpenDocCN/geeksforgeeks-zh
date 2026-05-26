# easy ui jquery validatepero widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery-validation ebox 小部件/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery EasyUI 设计一个验证框。验证框用于验证表单输入字段。

**jQuery 易 UI 下载:**

```html
https://www.jeasyui.com/download/index.php
```

**语法:**

```html
<input class="easyui-validatebox">
```

**属性:**

*   **必选:**指定提交前必须填写字段。
*   **延迟:**指定从最后一个输入值开始验证的延迟。
*   **missingMessage:** 这是文本框为空时出现的工具提示文本。
*   **invalidMessage:** 这是文本框内容无效时出现的工具提示文本。
*   **提示位置:**定义文本框内容无效时提示信息的位置。
*   **deltaX:** 这定义了工具提示在 X 方向的偏移。
*   **novalidate:** 指定是否关闭验证。
*   **可编辑:**指定用户是否可以直接在字段中输入文本。
*   **禁用:**指定是否禁用验证框。
*   **只读:**指定组件是否只读。
*   **验证创建:**指定创建组件后是否验证。
*   **validateonbull:**此指定失焦时是否验证。

#### **事件:**

*   **on beforevaluidate**:该事件在字段验证之前触发。
*   **onValidate:** 在字段上验证时触发此事件。

**方法:**

*   **选项:**返回选项对象。
*   **销毁:**移除并销毁组件。
*   **验证:**进行验证，确定文本框内容是否有效。
*   **isValid:** 调用 validate 方法并返回验证结果。
*   **启用验证:**启用验证。
*   **禁用验证:**禁用验证。
*   **重置验证:**重置验证。
*   **启用:**启用组件。
*   **禁用:**禁用组件。
*   **只读:**启用/禁用只读模式

**进场:**

*   首先，添加项目所需的 jQuery Easy UI 脚本。