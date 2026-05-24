# 如何在 C# 中设置文本框的前景色？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中文本框的前景色/](https://www.geeksforgeeks.org/how-to-set-the-foreground-color-of-the-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以借助 **ForeColor 属性**设置文本框的前景色，这使得您的文本框更具吸引力。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是设置文本框的 ForeColor 属性，如下步骤所示:

*   **步骤 1:** 创建窗口表单。如下图所示:
    **Visual Studio->File->New->Project->windows formapp**
    ![](img/1360c045c6c2debb857f904eacbae56c.png)
*   **步骤 2:** 从工具箱中拖动文本框控件，并将其放到窗口窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 TextBox 控件。如下图所示:
    ![](img/8e87d7ada0cbe1b13c3da2e0ee56d22e.png)
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the ForeColor property of the TextBox. As shown in the below image:
    ![](img/07fe77dd57c404206d2ff312187747da.png)

    **输出:**

    ![](img/31d0dd73707559fdbb1d2c1aeccddfe7.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的 ForeColor 属性:

```cs
public override System.Drawing.Color ForeColor { get; set; }

```

这里，颜色用于表示文本框的前景色。以下步骤用于设置文本框的前颜色属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **第二步:**创建文本框后，设置文本框类提供的文本框的 ForeColor 属性。

    ```cs
    // Set ForeColor property
    Mytextbox.ForeColor = Color.Red;

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
            Mylablel.Text = "Enter Name";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.ForeColor = Color.Red;
            Mytextbox.AutoSize = true;
            Mytextbox.Name = "text_box1";
            Mytextbox.Font = new Font("Broadway", 12);

            // Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
    ```

    **输出:**

    ![](img/418fb377d96fbb69da272f4b6bbd9b13.png)