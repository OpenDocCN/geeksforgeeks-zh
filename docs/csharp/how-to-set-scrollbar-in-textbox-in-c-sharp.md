# 如何在 C# 中设置 TextBox 中的滚动条？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 文本框中的滚动条/](https://www.geeksforgeeks.org/how-to-set-scrollbar-in-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，当您使用多行文本框时，可以借助文本框的**滚动条属性**来设置滚动条。此属性的默认值在 Windows 窗体中，您可以通过两种不同的方式设置此属性:

**1。设计时:**设置文本框的滚动条属性是最简单的方法，如以下步骤所示:

*   **步骤 1:** 创建窗口表单。
    **Visual Studio - >文件- >新建- >项目- >窗口形式程序**
    T6】
*   **步骤 2:** 从工具箱中拖动文本框控件，并将其放到窗口窗体上。您可以根据需要将文本框放置在 windows 窗体上的任何位置。如下图所示:
    ![](img/8e87d7ada0cbe1b13c3da2e0ee56d22e.png)
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the ScrollBars property of the TextBox.
    ![](img/8d73184737831805fce2440e912ebaf3.png)

    **输出:**
    ![](img/ea5561e205ef5204b0c35d0d849185ed.png)

**注意:**请记住，无论 scroll bars 属性的值如何，如果 WordPress 属性设置为 true，水平滚动条都不会显示。

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的滚动条属性:

```cs
public System.Windows.Forms.ScrollBars ScrollBars { get; set; }
```

这里，滚动条表示滚动条枚举值，指示多行文本框控件是不带滚动条、水平滚动条还是垂直滚动条，或者两者都没有。如果分配给属性的值不在枚举的有效值范围内，它将引发*InvalidEnumArgumentException*。以下步骤用于设置文本框的滚动条属性:

*   **步骤 1 :** 使用文本框类提供的*文本框()*构造函数创建一个文本框。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **步骤 2 :** 创建文本框后，设置文本框类提供的文本框的滚动条属性。

    ```cs
    // Set ScrollBars property
    Mytextbox.ScrollBars = ScrollBars.Vertical;

    ```

*   **Step 3 :** And last add this textbox control to from using Add() method.

    ```cs
    // Add this textbox to form
    this.Controls.Add(Mytextbox);

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

    namespace my {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the properties of Lable1
            Label Mylablel = new Label();
            Mylablel.Location = new Point(96, 54);
            Mylablel.Text = "Introduction";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.ForeColor = Color.DarkOliveGreen;
            Mytextbox.Height = 100;
            Mytextbox.Width = 200;
            Mytextbox.Name = "text_box1";
            Mytextbox.Multiline = true;
            Mytextbox.ScrollBars = ScrollBars.Vertical;

            // Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
    ```

    **输出:**

    ![](img/a43c389ba0f4a84e3615e29d263537e0.png)