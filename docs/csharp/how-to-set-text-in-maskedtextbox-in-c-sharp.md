# 如何在 C# 中设置 MaskedTextBox 中的 Text？

> 原文:[https://www . geesforgeks . org/how-set-text-in-masketextbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-set-text-in-maskedtextbox-in-c-sharp/)

在 C# 中，MaskedTextBox 控件为表单上的用户输入(如日期、电话号码等)提供了一个验证过程。或者换句话说，它被用来提供区分正确和不正确用户输入的屏蔽。在掩码文本框控件中，您可以使用将向用户显示的**文本属性**来设置掩码文本框中的文本。这是 MaskedTextBox 类的默认绑定属性。从该属性中检索的字符串使用诸如掩码、文本掩码格式等格式属性进行格式化。您可以通过两种不同的方式设置此属性:

**1。设计时:**在掩码文本框中设置文本是最简单的方法，如下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **Step 2:** Next, drag and drop the MaskedTextBox control from the toolbox on the form as shown in the below image:

    ![](img/696b640abfbffd1882d7239ad47f0669.png)

*   **Step 3:** After drag and drop you will go to the properties of the MaskedTextBox and set the text in the MaskedTextBox as shown in the below image:

    ![](img/562fa4e40f4945a11109c6044df8a882.png)

    **输出:**

    ![](img/b18e9239e10583bb6742d93e8710aaf8.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 MaskedTextBox 控件中的文本:

```cs
public override string Text { get; set; }
```

该属性的值为*系统。字符串*类型，将显示给用户。此属性的默认值为空。以下步骤显示了如何动态设置掩码文本框中的文本:

*   **步骤 1:** 使用 masketextbox()构造函数创建一个 masketextbox，该构造函数由 masketextbox 类提供。

    ```cs
    // Creating a MaskedTextBox
    MaskedTextBox m = new MaskedTextBox();

    ```

*   **步骤 2:** 创建 masketextbox 后，设置 masketextbox 类提供的 masketextbox 的 Text 属性。

    ```cs
    // Setting the text
    m.Text = "GeeksforGeeks";

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

    namespace WindowsFormsApp38 {

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

            // Creating and setting the 
            // properties of the Label
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
            m.Text = "GeeksforGeeks";
            m.TextAlign = HorizontalAlignment.Right;
            m.Size = new Size(176, 20);
            m.Name = "MyBox";
            m.BorderStyle = BorderStyle.Fixed3D;
            m.BackColor = Color.LightBlue;
            m.ForeColor = Color.HotPink;
            m.Font = new Font("Bell MT", 18);

            // Adding MaskedTextBox
            // control on the form
            this.Controls.Add(m);
        }
    }
    }
    ```

    **输出:**

    ![](img/4d03e78f38fd5b52f67cbf775484b9d0.png)