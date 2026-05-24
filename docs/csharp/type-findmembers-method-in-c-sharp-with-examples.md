# 类型。C# 中的 FindMembers()方法及示例

> 原文:[https://www . geesforgeks . org/type-find members-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/type-findmembers-method-in-c-sharp-with-examples/)

**类型。find MemberTypes(member types，BindingFlags，MemberFilter，Object)方法**用于返回指定成员类型的 MemberInfo 对象的筛选数组。
**语法:**

> 公共虚拟系统。反射。成员信息[]查找成员(系统。反射。成员类型成员类型，系统。反射。绑定标签绑定标签，系统。反射. MemberFilter 筛选器，对象 filter criteria)；

**参数:**

*   **memberType:** 表示应该搜索什么类型的成员。
*   **bindingAttr:** 用于指定如何进行搜索，或者 Zero，返回 null。
*   **过滤器:**进行比较，如果当前被检查的成员符合过滤器标准，则返回真，否则返回假。
*   **筛选条件:**确定成员是否返回到 MemberInfo 对象数组中的搜索条件。

以下**绑定标签**过滤标志可用于定义搜索中包括哪些成员:

*   您必须指定**绑定标签。实例**或**装订标签。静态**为了得到回报。
*   指定**绑定标签。实例**在搜索中包含实例成员。
*   指定**绑定标签。静态**在搜索中包含静态成员。
*   指定**绑定标签。公共**将公共成员纳入搜索。
*   指定**绑定标签。非公共**在搜索中包含非公共成员(即私有、内部和受保护成员)。

**返回值:**该方法返回指定成员类型的成员信息对象的过滤数组。或者是 MemberInfo 类型的空数组，
**异常:**如果*过滤器*为空，则此方法抛出 **ArgumentNullException** 。
**示例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.FindMembers(MemberTypes,
// BindingFlags, MemberFilter,
// Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(string);

        // Creating try-catch block for handling Exception
        try {

            // Declaring and initializing the object of MemberTypes
            // that indicates the type of member to search for.
            MemberTypes mt = MemberTypes.All;

            // Declaring and initializing the object of BindingFlags
            // that specify how the search is conducted.
            BindingFlags ba = BindingFlags.Public
                          | BindingFlags.Instance;

            // Declaring and initializing MemberFilter
            // which help the delegate that compares
            // the MemberInfo against filterCriteria.
            MemberFilter mf = new MemberFilter(Search);

            // Declaring and initializing object of filterCriteria
            // the search criteria that determines whether a member is
            // returned in the array of MemberInfo objects or not
            object filterCriteria = "Equals";

            // Getting filterd array of MemberInfo by
            // using FindMembers() Method
            MemberInfo[] info = objType.FindMembers(mt, ba, mf, filterCriteria);

            // Display the Result
            for (int index = 0; index < info.Length; index++)
                Console.WriteLine("Result of FindMembers -  {0}",
                                        info[index].ToString());
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining MyInterfaceFilter
    // which helps to fix the certain condition
    // on which filtration took place
    public static bool Search(MemberInfo info, Object obj)
    {

        // Compare the name of the member
        // function with the filter criteria.
        if (info.Name.ToString() == obj.ToString())
            return true;
        else
            return false;
    }
}
```

**Output:** 

```cs
Result of FindMembers -  Boolean Equals(System.Object)
Result of FindMembers -  Boolean Equals(System.String)
Result of FindMembers -  Boolean Equals(System.String, System.StringComparison)
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . find members？view=netcore-3.0](https://docs.microsoft.com/en-us/dotnet/api/system.type.findmembers?view=netcore-3.0)