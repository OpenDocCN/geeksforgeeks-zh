# 在安卓系统中使用自定义数组编辑器的 GridView 示例

> 原文：[https://www.geeksforgeeks.org/gridview-using-custom-arrayadapter-in-android-with-example/](https://www.geeksforgeeks.org/gridview-using-custom-arrayadapter-in-android-with-example/)

本文将构建一个应用程序来演示`GridView`中`CustomArrayAdapter`的使用。`GridViews`是以二维（行和列）显示视图的视图容器，它们在我的 android 应用程序中使用，一个简单的例子是 gallery 应用程序。适配器将用户界面元素与数据源连接起来，它帮助我们填充数据。例如，当用户滚动图库应用程序时，`GridView`会自动填充，而无需指定任何内容。有不同的适配器命名一些。

*   `ArrayAdapter`
*   `BaseAdapter`
*   `CustomArrayAdapter`

本文将介绍`CustomArrayAdapter`。

### 为什么要使用自定义数组适配器？

安卓已经提供了一个[`ArrayAdapter`](https://www.geeksforgeeks.org/arrayadapter-in-android-with-example/)的实现，只需下面演示的一行就可以使用。当我们有单个项目的列表时，我们可以使用`ArrayAdapter`。例如，电话联系人、国家或姓名的列表。下面是用于显示文本数据的数组适配器的语法。

> **语法:**
>
> `ArrayAdapter(Context context, int resource, int textViewResourceId, T[] objects)`
>
> **参数:**
>
> **context:** 是正在使用的应用程序上下文
>
> **resource:** 第二个参数是用于设置布局的资源 id（XML 文件）。
>
> **textViewResourceId:** 将显示数据的文本视图元素的标识
>
> **objects:** 是存储在数组中的数据元素。

这个方法的问题或限制我们不能使用复杂的布局，例如，想象我们正在构建一个像网飞或 prime 这样的应用程序，其中每个元素由许多元素组成，例如`ImageView`、`TextView`等。对于`ArrayAdapter`的简单实现，这样复杂的视图是不可能的。为此，我们需要通过扩展`ArrayAdapter`类来创建我们的自定义适配器。下面的代码显示了自定义数组适配器的结构。

### Java 代码示例

```java
public class CustomAdapter extends ArrayAdapter
{

public CustomAdapter(Context context, int resource, List objects)
    {
        super(context, resource, objects);
    }
    @Override public int getCount()
    {
        return super.getCount();
    }

@Override
    public View getView(int position, View convertView, ViewGroup parent)
    {
        return super.getView(position, convertView, parent);
    }
}
```