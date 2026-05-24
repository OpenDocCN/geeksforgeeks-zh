# 如何在 C# 中设置 RichTextBox 的边框样式？

> 原文:[https://www . geeksforgeeks . org/how-style-the-richtextbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-style-the-border-of-the-richtextbox-in-c-sharp/)

在 C# 中，RichTextBox 控件是一个文本框，它为您提供富文本编辑控件和高级格式功能，还包括加载富文本格式(RTF)文件。或者换句话说，RichTextBox 控件允许您显示或编辑流内容，包括段落、图像、表格等。在 RichTextBox 中，您可以使用**边框样式属性**设置 RichTextBox 控件的边框样式。此属性有三个不同的值，在 BorderStyle 枚举下定义，这些值是:

*   无值表示无边框。
*   三维边框的固定三维值。
*   单行边框的固定单一值。

此属性的默认值为固定 3D。您可以通过两种不同的方式设置此属性:

**1。设计时:**这是设置 RichTextBox 边框样式的最简单方法，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **Step 2:** Next, drag and drop the RichTextBox control from the toolbox to the form as shown in the below image:

    ![](img/c052e8376f8a764b03990cf22ee63166.png)

*   **Step 3:** After drag and drop you will go to the properties of the RichTextBox and style the border of the RichTextBox as shown in the below image:

    ![](img/e00b664096315d295defee2131ac7948.png)

    **输出:**

    ![](img/466b0a117df62c8d233c6d09b778980f.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置 RichTextBox 控件的边框样式:

```cs
public string Name { get; set; }
```

这里，BorderStyle 表示 RichTextBox 控件的边框样式。如果此属性的值不属于 BorderStyle 枚举值，它将引发*InvalidEnumArgumentException*。以下步骤显示了如何动态设置 RichTextBox 边框的样式:

*   **步骤 1:** 使用 RichTextBox()构造函数创建一个 RichTextBox，该构造函数由 RichTextBox 类提供。

    ```cs
    // Creating a RichTextBox
    RichTextBox rbox = new RichTextBox();

    ```

*   **步骤 2:** 创建 RichTextBox 后，设置 RichTextBox 类提供的 RichTextBox 的 BorderStyle 属性。

    ```cs
    // Setting the border style
    rbox.BorderStyle = BorderStyle.FixedSingle;

    ```

*   **第 3 步:**最后使用以下语句将这个 RichTextBox 控件添加到表单中:

    ```cs
    // Adding a RichTextBox
    // control to the form
    this.Controls.Add(rbox);

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

namespace WindowsFormsApp51 {

public partial class Form1 : Form {

    public Form1()
    {
        InitializeComponent();
    }

    private void Form1_Load(object sender, EventArgs e)
    {
        // Creating and setting the
        // properties of the label
        Label lb = new Label();
        lb.Location = new Point(251, 70);
        lb.Text = "Enter Introduction";

        // Adding this label in the form
        this.Controls.Add(lb);

        // Creating and setting the
        // properties of RichTextBox
        RichTextBox rbox = new RichTextBox();
        rbox.Location = new Point(236, 97);
        rbox.Size = new Size(278, 115);
        rbox.BorderStyle = BorderStyle.FixedSingle;
        rbox.ForeColor = Color.Green;
        rbox.Text = "Welcome to GeeksforGeeks Portal";

        // Adding this RichTextBox
        // in the form
        this.Controls.Add(rbox);
    }
}
}
```

**输出:**

![](img/9e903afe5a869d2f97a7bfff8a0a6dae.png)