# 使用 LINQ 打印非通用集合列表的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-print-the-list-of-non-generic-collections-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-list-of-non-generic-collections-using-linq/)

非泛型集合在 `System.Collections` 命名空间中定义。它是一种通用的数据结构，对对象引用起作用，因此它可以处理任何类型的对象，但不是以类型安全的方式。非泛型集合由 `System.Collections` 命名空间中的接口和类定义。我们可以通过使用 `AppDomain` 和 `CurrentDomain` 来获得实现 `IEnumerable` 接口的所有类型。这两个域将获得集合列表。除此之外，我们还将使用 `IEnumerable`。`IEnumerable` 是 C# 中的一个接口，用于定义一个只允许对集合进行只读访问的方法，然后实现该接口的集合可以与 `foreach` 语句一起使用。该接口包含在 `System.Collections` 命名空间中。`IEnumerable` 接口是一个通用接口，允许在泛型或非泛型列表上循环。

**语法**:

> `public IEnumerator GetEnumerator()`
> 
> {
> 
> //语句
> 
> }

**返回值:** 这个方法返回一个遍历集合的枚举数。

**示例:**

## C\#

```cs
// C# program to illustrate how to display the 
// list of non-generic collections using LINQ
using System;
using System.IO;
using System.Linq;
using System.Collections;

class GFG{

    public static void Main(string[] args)
    {

        // Get the type of IEnumerable
        var result = typeof(IEnumerable);

        // Get the domain
        var nonGenCollection = AppDomain.CurrentDomain.GetAssemblies().SelectMany(
                               x => x.GetTypes()).Where(x => result.IsAssignableFrom(x));

        // Display all the types using for loop
        foreach (var detail in nonGenCollection)
        {
            Console.WriteLine("---> " + detail.FullName);
        }
    }
}
```

**解释:** 在这个例子中，我们定义了一个 `nonGenCollection` 变量，它将通过使用 `AppDomain.CurrentDomain.GetAssemblies()` 方法获得所有的 `IEnumerable` 类型。这个方法将获得所有非泛型集合的列表。然后，我们使用 `foreach` 循环迭代它，以显示集合的全名。

**输出:**

```cs
---> Mono.Security.X509.X509CertificateCollection
---> Mono.Security.X509.X509ExtensionCollection
---> System.ArraySegment`1
---> System.String
---> System.Array
---> System.Resources.IResourceReader
---> System.Resources.ResourceFallbackManager
---> System.Resources.ResourceReader
---> System.Resources.ResourceSet
---> System.Resources.RuntimeResourceSet
---> System.Reflection.TypeInfo+<GetDeclaredMethods>d__9
---> System.Reflection.TypeInfo+<get_DeclaredNestedTypes>d__23
---> System.Reflection.Assembly+<get_DefinedTypes>d__150
---> System.Threading.ThreadPool+<EnumerateQueuedWorkItems>d__21
---> System.Threading.Tasks.IProducerConsumerQueue`1
---> System.Threading.Tasks.MultiProducerMultiConsumerQueue`1
---> System.Threading.Tasks.SingleProducerSingleConsumerQueue`1
---> System.Threading.Tasks.ThreadPoolTaskScheduler+<FilterTasksFromWorkItems>d__7
---> System.IO.Iterator`1
---> System.IO.FileSystemEnumerableIterator`1
---> System.IO.DirectoryInfo+<CreateEnumerateDirectoriesIterator>d__39
---> System.IO.DirectoryInfo+<CreateEnumerateFilesIterator>d__43
---> System.IO.DirectoryInfo+<EnumerateFileSystemInfos>d__47
---> System.IO.File+<ReadLines>d__58
---> System.Runtime.Serialization.SurrogateHashtable
---> System.Runtime.Remoting.Channels.AggregateDictionary
---> System.Runtime.Remoting.Channels.BaseChannelObjectWithProperties
---> System.Runtime.Remoting.Channels.BaseChannelSinkWithProperties
---> System.Runtime.Remoting.Channels.BaseChannelWithProperties
---> System.Runtime.Remoting.Messaging.ConstructionCallDictionary
---> System.Runtime.Remoting.Messaging.MCMDictionary
---> System.Runtime.Remoting.Messaging.MethodCallMessageWrapper+DictionaryWrapper
---> System.Runtime.Remoting.Messaging.MessageDictionary
---> System.Runtime.Remoting.Messaging.MethodReturnDictionary
---> System.Runtime.Remoting.Messaging.MethodReturnMessageWrapper+DictionaryWrapper
---> System.Security.NamedPermissionSet
---> System.Security.PermissionSet
---> System.Security.Policy.ApplicationTrustCollection
Press enter to continue ......
```