# 如何在 C# 中设置 MaskedTextBox 的可见性？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中 maskedtextbox 的可见性/](https://www.geeksforgeeks.org/how-to-set-the-visibility-of-maskedtextbox-in-c-sharp/)

在 C# 中，MaskedTextBox 控件为表单上的用户输入(如日期、电话号码等)提供了一个验证过程。或者换句话说，它被用来提供区分正确和不正确用户输入的屏蔽。在掩码文本框控件中，您可以使用掩码文本框控件提供的**可见属性**来设置掩码文本框的可见性。
如果这个属性的值被设置为 true，那么 MaskedTextBox 控件及其子控件在屏幕上是可见的。如果这个属性的值被设置为 false，那么 MaskedTextBox 控件及其子控件在屏幕上是不可见的。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是设置 MaskedTextBox 控件的 Visible 属性值，如下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:

    **Visual Studio - >文件- >新建- >项目->window formapp**

    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the MaskedTextBox control from the toolbox on the form as shown in the below image:

    ![](img/696b640abfbffd1882d7239ad47f0669.png)

*   **Step 3:** After drag and drop you will go to the properties of the MaskedTextBox and set the value of Visible property of MaskedTextBox control as shown in the below image:

    ![](img/11bbcd98feab2738c74a85f7cd901c66.png)

    **输出:**

    ![](img/29fa5667cded1b323ee12a3c3c671775.png)

**2。运行时:**比上面的方法稍微复杂一点。在这个方法中，您可以在给定语法的帮助下，以编程方式设置 MaskedTextBox 控件的可见性:

```cs
public bool Visible { get; set; }
```

该属性的值为*系统。布尔*类型，非真即假。以下步骤显示了如何动态设置 MaskedTextBox 控件的可见性:

*   **步骤 1:** 使用 masketextbox()构造函数创建一个 masketextbox，该构造函数由 masketextbox 类提供。

    ```cs
    // Creating a MaskedTextBox
    MaskedTextBox m = new MaskedTextBox();

    ```

*   **步骤 2:** 创建 masketextbox 后，设置 masketextbox 类提供的 masketextbox 的 Visible 属性。

    ```cs
    // Setting the visibility
    m.Visible = false;

    ```

*   **Step 3:** And last add this MaskedTextBox control to the form using the following statement:

    ```cs
    // Adding MaskedTextBox 
    // control on the form
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
            m.Mask = "000000000";
            m.Size = new Size(176, 20);
            m.Name = "MyBox";
            m.BorderStyle = BorderStyle.Fixed3D;
            m.Visible = false;
            m.Font = new Font("Bell MT", 18);

            // Adding MaskedTextBox 
            // control on the form
            this.Controls.Add(m);
        }
    }
    }
    ```

    **输出:**

    在将“可见”属性值设置为 false 之前:

    ![](img/65e770988058132414b30a85e223044c.png)

    将“可见”属性值设置为 false 后:

    ![](img/5d474a9947657cb3f038fcdca798daeb.png)