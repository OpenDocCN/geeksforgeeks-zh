# 如何在 C# 的文本框中设置默认密码字符？

> 原文:[https://www . geeksforgeeks . org/如何设置默认密码-c-sharp 中的文本框字符/](https://www.geeksforgeeks.org/how-to-set-default-password-character-in-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以通过使用文本框的 *UseSystemPasswordChar 属性*来设置一个值，该值表示文本框控件中的文本是否应显示为默认密码字符。如果将该属性的值设置为 true，则文本框控件中的文本应该显示为默认密码字符，否则设置为 false。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**设置文本框的 UseSystemPasswordChar 属性的最简单方法如下步骤所示:

*   **步骤 1:** 创建窗口表单。
    **Visual Studio - >文件- >新建- >项目- >窗口形式程序**
    T6】
*   **步骤 2:** 从工具箱中拖动文本框控件，并将其放到窗口窗体上。您可以根据需要将文本框放置在 windows 窗体上的任何位置。如下图所示:
    ![](img/8e87d7ada0cbe1b13c3da2e0ee56d22e.png)
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the UseSystemPasswordChar property of the TextBox. As shown in the below image:
    ![](img/fd89fbb50d5b9ce1e5300c0158640187.png)

    **输出:**
    ![](img/2e14e30b187caaf8ccf83a3e9cd4d7dd.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的 *UseSystemPasswordChar* 属性:

```cs
public bool UseSystemPasswordChar { get; set; }
```

这里，该属性的值为*系统。布尔*类型。以下步骤用于设置文本框的 UseSystemPasswordChar 属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **第二步:**创建文本框后，设置文本框类提供的文本框的 UseSystemPasswordChar 属性。

    ```cs
    // Set UseSystemPasswordChar property
    Mytextbox.UseSystemPasswordChar = true;

    ```

*   **Step 3 :** And last add this textbox control to from using *Add()* method.

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
            Mylablel.Text = "Enter Password";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.ForeColor = Color.DarkOliveGreen;
            Mytextbox.AutoSize = true;
            Mytextbox.Name = "text_box1";
            Mytextbox.UseSystemPasswordChar = true;

            // Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
    ```

    **输出:**

    ![](img/f5c7bb2d70f1e8c82603998a0abdeffa.png)