# 如何在 C# 中设置 MaskedTextBox 中的提示字符？

> 原文:[https://www . geeksforgeeks . org/如何设置 masketextbox-in-c-sharp 中的提示字符/](https://www.geeksforgeeks.org/how-to-set-the-prompt-character-in-maskedtextbox-in-c-sharp/)

在 C# 中，MaskedTextBox 控件为表单上的用户输入(如日期、电话号码等)提供了一个验证过程。或者换句话说，它被用来提供区分正确和不正确用户输入的屏蔽。在 masketextbox 控件中，您可以使用 masketextbox 控件提供的 **PromptChar 属性**设置一个字符，该字符表示 masketextbox 中没有用户输入。此属性的默认值是下划线(_)。您可以通过两种不同的方式设置此属性:

**1。设计时:**设置 MaskedTextBox 控件的 PromptChar 属性的值是最简单的方法，如下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:

    **Visual Studio - >文件- >新建- >项目->window formapp**

    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the MaskedTextBox control from the toolbox on the form. As shown in the below image:

    ![](img/696b640abfbffd1882d7239ad47f0669.png)

*   **Step 3:** After drag and drop you will go to the properties of the MaskedTextBox and set the value of the PromptChar property of MaskedTextBox control as shown in the below image:

    ![](img/b0bedf46d8e3201b8b4a400777f03809.png)

    **输出:**

    ![](img/1b878347b2b440b755a1ec4fa4a41036.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 MaskedTextBox 控件的提示字符:

```cs
public char PromptChar { get; set; }
```

这里，Char 代表提示字符。如果提示字符的值与密码字符相似，那么它将抛出*无效操作异常*。如果由*is validapasswordchar(Char)*方法确定的提示字符的值无效，也抛出 *ArgumentException* 。以下步骤显示了如何动态设置 MaskedTextBox 控件的提示字符:

*   **步骤 1:** 使用 masketextbox()构造函数创建一个 masketextbox，该构造函数由 masketextbox 类提供。

    ```cs
    // Creating a MaskedTextBox
    MaskedTextBox m = new MaskedTextBox();

    ```

*   **步骤 2:** 创建 masketextbox 后，设置 masketextbox 类提供的 masketextbox 的 PromptChar 属性。

    ```cs
    // Setting the Prompt Character
    m.PromptChar = '-';

    ```

*   **Step 3:** And last add this MaskedTextBox control to the form using the following statement:

    ```cs
    // Adding MaskedTextBox control on the form
    this.Controls.Add(m);

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

    namespace WindowsFormsApp39 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the
            // properties of the Label
            Label l1 = new Label();
            l1.Location = new Point(413, 98);
            l1.Size = new Size(176, 20);
            l1.Text = " Example";
            l1.Font = new Font("Bell MT", 12);

            // Adding label on the form
            this.Controls.Add(l1);

            // Creating and setting
            // the properties of Label
            Label l2 = new Label();
            l2.Location = new Point(242, 135);
            l2.Size = new Size(126, 20);
            l2.Text = "Phone number:";
            l2.Font = new Font("Bell MT", 12);

            // Adding label on the form
            this.Controls.Add(l2);

            // Creating and setting the
            // properties of MaskedTextBox
            MaskedTextBox m = new MaskedTextBox();
            m.Location = new Point(374, 137);
            m.Mask = "000000000";
            m.Size = new Size(176, 20);
            m.Name = "MyBox";
            m.BorderStyle = BorderStyle.Fixed3D;
            m.PromptChar = '-';
            m.Font = new Font("Bell MT", 18);

            // Adding MaskedTextBox 
            // control on the form
            this.Controls.Add(m);
        }
    }
    }
    ```

    **输出:**

    ![](img/fca77cabc01ee10f6a7ea58b98ad2622.png)