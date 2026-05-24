# 如何在 C# 中设置 MaskedTextBox 中的只读内容？

> 原文:[https://www . geesforgeks . org/how-set-read-only-content-in-masketextbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-set-read-only-content-in-maskedtextbox-in-c-sharp/)

在 C# 中，MaskedTextBox 控件为表单上的用户输入(如日期、电话号码等)提供了一个验证过程。或者换句话说，它被用来提供区分正确和不正确用户输入的屏蔽。在掩码文本框控件中，可以使用 **ReadOnly 属性**将掩码文本框中的文本设置为只读。如果该属性的值为真，则掩码文本框中的文本是只读的。否则，假的。此属性的默认值为 false。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是设置 MaskedTextBox 控件的 ReadOnly 属性值，如下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:

    **Visual Studio - >文件- >新建- >项目->window formapp**

    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the MaskedTextBox control from the toolbox on the form as shown in the below image:

    ![](img/696b640abfbffd1882d7239ad47f0669.png)

*   **Step 3:** After drag and drop you will go to the properties of the MaskedTextBox and set the value of ReadOnly property of MaskedTextBox control as shown in the below image:

    ![](img/6e1129f588d111bde7c95c8811ad1b03.png)

    **输出:**
    ![](img/6637714f7564399dfa1772739f4cdf64.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 MaskedTextBox 控件的 ReadOnly 属性值:

```cs
public bool ReadOnly { get; set; }
```

该属性的值为*系统。布尔*类型，非真即假。以下步骤显示了如何动态设置 MaskedTextBox 控件的 ReadOnly 属性值:

*   **步骤 1:** 使用 masketextbox()构造函数创建一个 masketextbox，该构造函数由 masketextbox 类提供。

    ```cs
    // Creating a MaskedTextBox
    MaskedTextBox m = new MaskedTextBox();

    ```

*   **步骤 2:** 创建 masketextbox 后，设置 masketextbox 类提供的 masketextbox 的 ReadOnly 属性。

    ```cs
    // Setting the ReadOnly property
    m.ReadOnly = true;

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
            m.Text = "999999999";
            m.ReadOnly = true;
            m.Font = new Font("Bell MT", 18);

            // Adding MaskedTextBox 
            // control on the form
            this.Controls.Add(m);
        }
    }
    }
    ```

    **输出:**

    ![](img/fdf73269ab0bda654adccc71cba790b3.png)