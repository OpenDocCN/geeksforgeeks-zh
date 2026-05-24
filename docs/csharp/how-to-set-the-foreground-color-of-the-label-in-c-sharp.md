# 如何在 C# 中设置标签的前景色？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中标签的前景色/](https://www.geeksforgeeks.org/how-to-set-the-foreground-color-of-the-label-in-c-sharp/)

在 Windows 窗体中，Label 控件用于在窗体上显示文本，它不参与用户输入或鼠标或键盘事件。您可以使用**前景色属性**设置标签控件的前景色。这让你的标签更有吸引力。它是一个环境属性，这意味着如果我们不设置该属性的值，它将自动从父控件中检索。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置 Label 控件的 ForeColor 属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f1d477c51402b2df11d7ed28eee617fe.png)
*   **步骤 2:** 从工具箱中拖动标签控件，并将其放到窗口窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 Label 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Label control to set the ForeColor property of the Label.
    ![](img/90572344e7ccaa734f09300d5492056e.png)

    **输出:**
    ![](img/aed58ad317c90ec30ceff7848172baa2.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置 Label 控件的前景色:

```cs
public virtual System.Drawing.Color ForeColor { get; set; }
```

这里，颜色表示标签的前景色。以下步骤用于设置标签的前颜色属性:

*   **步骤 1:** 使用标签类提供的标签()构造函数创建标签。

    ```cs
    // Creating label using Label class
    Label mylab = new Label();

    ```

*   **第 2 步:**创建标签后，设置标签类提供的标签的前景色属性。

    ```cs
    // Set ForeColor property of the label
    mylab.ForeColor = Color.DarkBlue;

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
            mylab.BackColor = Color.LightBlue;
            mylab.Font = new Font("Calibri", 12);
            mylab.ForeColor = Color.DarkBlue;

            // Adding this control to the form
            this.Controls.Add(mylab);
        }
    }
    }
    ```

    **输出:**
    ![](img/41f6ef583670e07da45a137b19960f3c.png)