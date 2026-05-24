# 如何在 C# 中设置标签的大小？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中标签的大小/](https://www.geeksforgeeks.org/how-to-set-the-size-of-the-label-in-c-sharp/)

在 Windows 窗体中，Label 控件用于在窗体上显示文本，它不参与用户输入或鼠标或键盘事件。您可以使用**大小属性**设置标签控件的大小。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置标签控件的大小属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f1d477c51402b2df11d7ed28eee617fe.png)
*   **步骤 2:** 从工具箱中拖动标签控件，并将其放到窗口窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 Label 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Label control to set the Size property of the Label.
    ![](img/58e35d616989cadf818d7f8c36453f89.png)

    **输出:**
    ![](img/cda6ddd65ba795320dbd87bee48f7574.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置 Label 控件的大小:

```cs
public System.Drawing.Size Size { get; set; }
```

这里，尺寸以像素为单位表示标签的高度和宽度。以下步骤用于设置标签的“大小”属性:

*   **步骤 1:** 使用标签类提供的标签()构造函数创建标签。

    ```cs
    // Creating label using Label class
    Label mylab = new Label();

    ```

*   **步骤 2:** 创建标签后，设置标签类提供的标签的大小属性。

    ```cs
    // Set Size property of the label
    mylab.Size = new Size(120, 25);

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