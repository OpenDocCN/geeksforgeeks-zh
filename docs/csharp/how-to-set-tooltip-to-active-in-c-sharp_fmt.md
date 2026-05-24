# 如何在 C# 中将 ToolTip 设置为 active？

> 原文: [https://www.geeksforgeeks.org/how-to-set-tooltip-to-active-in-c-sharp/](https://www.geeksforgeeks.org/how-to-set-tooltip-to-active-in-c-sharp/)

在 Windows 窗体中，工具提示代表一个微小的弹出框，当您将指针或光标放在控件上时，该框会出现。该控件的目的是提供有关 Windows 窗体中控件的简要说明。在工具提示中，可以使用 `Active` 属性检查工具提示是否活动。

该属性的默认值为 `true`。当 `Active` 属性设置为 `true` 时，意味着工具提示框将在屏幕上弹出；当 `Active` 属性设置为 `false` 时，意味着工具提示框不会在屏幕上弹出。您可以通过两种不同的方式设置此属性：

## 1. 设计时

最简单的方法是设置 `Active` 属性的值，如以下步骤所示：

*   **第一步:** 创建如下图所示的窗口表单:
    **Visual Studio -> File -> New -> Project -> Windows Forms App**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **第二步:** 从工具箱中拖动 `ToolTip` 并将其放到窗体上。当您将此 `ToolTip` 拖放到窗体上时，它将自动添加到当前 Windows 窗体中每个控件的属性（命名为 `ToolTip` 或 `ToolTip1`）中。
    ![](img/350d05c39f67ec9444b226e20fc599ec.png)
*   **第三步:** 拖放完成后，转到 `ToolTip` 的属性窗口并设置 `Active` 属性的值。
    ![](img/5b5fd5a4f3e91e384e236d08c92cbeb5.png)

**输出:**
![](img/a9c99fc5a64ebf4384226643a98c7da5.png)

## 2. 运行时

比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置工具提示的 `Active` 属性：

```cs
public bool Active { get; set; }
```

这里，该属性的值为 `System.Boolean` 类型。因此，要激活工具提示，请将该属性的值设置为 `true`。否则，`false`。以下步骤显示了如何动态设置工具提示的 `Active` 属性：

*   **步骤 1:** 使用 `ToolTip()` 构造函数创建工具提示，该构造函数由 `ToolTip` 类提供。

```cs
// Creating a ToolTip
ToolTip t = new ToolTip();
```

*   **第二步:** 创建工具提示后，设置 `ToolTip` 类提供的工具提示的 `Active` 属性。

```cs
// Setting the Active property
t.Active = true;
```

*   **步骤 3:** 最后，使用 `SetToolTip()` 方法将此 `ToolTip` 添加到控件。此方法包含控件名称和您希望在工具提示框中显示的文本。

```cs
t.SetToolTip(box1, "Name should be start with Capital letters");
```

**示例:**

```cs
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WindowsFormsApp33
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the 
            // properties of the Label
            Label l1 = new Label();
            l1.Location = new Point(140, 122);
            l1.Text = "Name";

            // Adding this Label control to the form
            this.Controls.Add(l1);

            // Creating and setting the
            // properties of the TextBox
            TextBox box1 = new TextBox();
            box1.Location = new Point(248, 119);
            box1.BorderStyle = BorderStyle.FixedSingle;

            // Adding this TextBox 
            // control to the form
            this.Controls.Add(box1);

            // Creating and setting the 
            // properties of the Label
            Label l2 = new Label();
            l2.Location = new Point(140, 152);
            l2.Text = "Password";

            // Adding this Label control to the form
            this.Controls.Add(l2);

            // Creating and setting the
            // properties of the TextBox
            TextBox box2 = new TextBox();
            box2.Location = new Point(248, 145);
            box2.BorderStyle = BorderStyle.FixedSingle;

            // Adding this TextBox 
            // control to the form
            this.Controls.Add(box2);

            // Creating and setting the
            // properties of the ToolTip
            ToolTip t = new ToolTip();
            t.Active = true;
            t.SetToolTip(box1, "Name should be start with Capital letters");
            t.SetToolTip(box2, "Password should be greater than 8 words");
        }
    }
}
```

**输出:**

![](img/47302d9af4fde14a29574bfff1cb3b67.png)