# 如何在 C# 的 RichTextBox 中添加文本？

> 原文:[https://www . geeksforgeeks . org/how-add-text-in-richtextbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-add-text-in-the-richtextbox-in-c-sharp/)

在 C# 中，RichTextBox 控件是一个文本框，它为您提供富文本编辑控件和高级格式功能，还包括加载富文本格式(RTF)文件。或者换句话说，RichTextBox 控件允许您显示或编辑流内容，包括段落、图像、表格等。在 RichTextBox 中，您可以使用**文本属性**在屏幕上显示的 RichTextBox 控件中添加文本。您可以通过两种不同的方式设置此属性:

**1。设计时:**在 RichTextBox 中添加文本是最简单的方法，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/fc5363a71d43167b6925e7d530d466f6.png)
*   **第 2 步:**从工具箱中拖动 RichTextBox 控件，并将其放到窗口窗体上。根据您的需要，您可以将 RichTextBox 控件放置在 windows 窗体上的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the RichTextBox control to add text in the RichTextBox control.
    ![](img/6ea2236bc6951add7da6e9c4d3e22046.png)

    **输出:**
    ![](img/4bbfccaaa3d7f4dc8b2ed67da5f5f6b8.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式在 RichTextBox 控件中添加文本:

```cs
public override string Text { get; set; }
```

这里，该属性的值为*系统。弦*型。以下步骤显示了如何动态设置 RichTextBox 的文本属性:

*   **步骤 1:** 使用 RichTextBox()构造函数创建一个 RichTextBox，该构造函数由 RichTextBox 类提供。

    ```cs
    // Creating RichTextBox using RichTextBox class constructor
    RichTextBox rbox = new RichTextBox();

    ```

*   **步骤 2:** 创建完 RichTextBox 后，设置 RichTextBox 类提供的 RichTextBox 的 Text 属性。

    ```cs
    // Adding text in the control box
    rbox.Text = "!..Welcome to GeeksforGeeks..!";

    ```

*   **Step 3:** And last add this RichTextBox control to the form using Add() method.

    ```cs
    // Add this RichTextBox to the form
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

    namespace WindowsFormsApp30 {

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
            lb.Text = "Enter Text";

            // Adding this label in the form
            this.Controls.Add(lb);

            // Creating and setting the
            // properties of RichTextBox
            RichTextBox rbox = new RichTextBox();
            rbox.Location = new Point(236, 97);
            rbox.ForeColor = Color.Red;
            rbox.Text = "!..Welcome to GeeksforGeeks..!";

            // Adding this RichTextBox in the form
            this.Controls.Add(rbox);
        }
    }
    }
    ```

    **输出:**

    ![](img/b19eff79a5182024f202548d5d8bce87.png)