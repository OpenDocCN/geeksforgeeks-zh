# 如何在 C# 中设置标签边框的样式？

> 原文:[https://www . geeksforgeeks . org/c-sharp 中标签边框的样式/](https://www.geeksforgeeks.org/how-to-style-the-border-of-label-in-c-sharp/)

在 Windows 窗体中，Label 控件用于在窗体上显示文本，它不参与用户输入或鼠标或键盘事件。您可以使用**边框样式属性**设置标签控件的边框样式。可以用三种不同的方式设置标签边框的样式，这些值由 BorderStyle 枚举提供:

*   **固定 3D:** 标签的边框为三维边框。
*   **FixedSingle:** 标签的边框为单线边框。
*   **无:**无边框标签。

此属性的默认值为 BorderStyle.None。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置标签控件的 BorderStyle 属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f1d477c51402b2df11d7ed28eee617fe.png)
*   **步骤 2:** 从工具箱中拖动标签控件，并将其放到窗口窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 Label 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Label control to set the BorderStyle property of the Label.
    ![](img/966d18de4f5d96f5d3935af3d4b480a3.png)

    **输出:**
    ![](img/1c06690f0cec6a936332f4bf8df691d7.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下以编程方式设置标签控件的边框样式:

```cs
public virtual System.Windows.Forms.BorderStyle BorderStyle { get; set; }
```

这里，边框样式表示边框样式值。如果分配给该属性的值不属于 BorderStyle 值，它将引发*InvalidEnumArgumentException*。以下步骤用于设置标签的边框样式属性:

*   **步骤 1:** 使用标签类提供的标签()构造函数创建标签。

    ```cs
    // Creating label using Label class
    Label mylab = new Label();

    ```

*   **步骤 2:** 创建标签后，设置标签类提供的标签的 BorderStyle 属性。

    ```cs
    // Set BorderStyle property of the label
    mylab.BorderStyle = BorderStyle.FixedSingle;

    ```

*   **Step 3:** And last add this Label control to form using Add() method.

    ```cs
    // Add this label to the form
    this.Controls.Add(mylab);

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

    namespace WindowsFormsApp16 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the label
            Label mylab = new Label();
            mylab.Text = "GeeksforGeeks";
            mylab.Location = new Point(222, 90);
            mylab.Size = new Size(120, 25);
            mylab.BorderStyle = BorderStyle.FixedSingle;

            // Adding this control to the form
            this.Controls.Add(mylab);
        }
    }
    }
    ```

    **输出:**
    ![](img/d3b2f1cb81f61a8d4361276988c987bb.png)