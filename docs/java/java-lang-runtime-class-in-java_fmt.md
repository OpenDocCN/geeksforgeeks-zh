# Java 中的 Java.lang.Runtime 类

> 原文: [https://www.geeksforgeeks.org/java-lang-runtime-class-in-java/](https://www.geeksforgeeks.org/java-lang-runtime-class-in-java/)

每个 Java 应用程序都有一个类 `Runtime` 的实例，它允许应用程序与运行该应用程序的环境交互。当前运行时间可以通过 `getRuntime()` 方法获取。

## Java Runtime 类的方法

**1) `public static Runtime getRuntime()`**
此方法返回与当前 Java 应用程序关联的实例或 `Runtime` 对象。

```java
// Java program to illustrate getRuntime()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // get the current runtime associated with this process
        Runtime run = Runtime.getRuntime();
        // print the current free memory for this runtime
        System.out.println("" + run.freeMemory());
    }
}
```

输出:

```java

```

**2) `public long freeMemory()`**
此方法返回 JVM (Java 虚拟机)中的空闲内存量。

```java
// Java program to illustrate freeMemory()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // print the number of free bytes
        System.out.println("" + Runtime.getRuntime().freeMemory());
    }
}
```

输出:

```java

```

**3) `public long totalMemory()`**
此方法返回 JVM (Java 虚拟机)中的总内存量。

```java
// Java program to illustrate totalMemory()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // print the number of total bytes
        System.out.println("" + Runtime.getRuntime().totalMemory());
    }
}
```

输出:

```java

```

**4) `public Process exec(String command) throws IOException`**
这个方法在单独的进程中执行给定的命令。

**异常:**
- `SecurityException`: 如果安全管理器存在，并且其 `checkExec` 方法不允许创建子进程。
- `IOException`: 如果出现 I/O 错误。
- `NullPointerException`: 如果命令为 `null`。
- `IllegalArgumentException`: 如果命令为空。

```java
// Java program to illustrate Process exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            // create a process and execute google-chrome
            Process process = Runtime.getRuntime().exec("google-chrome");
            System.out.println("Google Chrome successfully started");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:

```java
Google Chrome successfully started
```

**注意:** 替换为任何你想启动的软件。我在 Linux 和谷歌上工作——chrome 就是这样写的。可能在 windows/mac 上有所不同。

**5) `public void addShutdownHook(Thread hook)`**
这个方法注册一个新的虚拟机[关闭钩子](https://www.geeksforgeeks.org/jvm-shutdown-hook-java/)线程。

**异常:**
- `IllegalArgumentException`: 如果指定的钩子已经注册，或者可以确定钩子已经在运行或者已经在运行。
- `IllegalStateException`: 如果虚拟机已经处于关闭过程中。
- `SecurityException`: 如果安全管理器拒绝 `RuntimePermission("shutdownHooks")`。

```java
// Java program to illustrate addShutdownHook()
// method of Runtime class
public class GFG
{
    // a class that extends thread that is to be called when program is exiting
    static class Message extends Thread
    {
        public void run()
        {
            System.out.println("Program exiting");
        }
    }
    public static void main(String[] args)
    {
        try
        {
            // register Message as shutdown hook
            Runtime.getRuntime().addShutdownHook(new Message());

            // cause thread to sleep for 3 seconds
            System.out.println("Waiting for 5 seconds...");
            Thread.sleep(5000);
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:

```java
Waiting for 5 seconds...
Program exiting
```

**6) `public boolean removeShutdownHook(Thread hook)`**
此方法取消注册先前注册的虚拟机关闭钩子。

```java
// Java program to illustrate removeShutdownHook()
// method of Runtime class
public class GFG
{
    // a class that extends thread that is to be called when program is exiting
    static class Message extends Thread
    {
        public void run()
        {
            System.out.println("Program exiting");
        }
    }
    public static void main(String[] args)
    {
        try
        {
            Message p = new Message();
            // register Message as shutdown hook
            Runtime.getRuntime().addShutdownHook(p);

            // cause thread to sleep for 3 seconds
            System.out.println("Waiting for 5 seconds...");
            Thread.sleep(5000);

            // remove the hook
            Runtime.getRuntime().removeShutdownHook(p);
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:

```java
Waiting for 5 seconds...
```

**7) `public int availableProcessors()`**
此方法返回 JVM (Java 虚拟机)可用的处理器数量。

```java
// Java program to illustrate availableProcessors()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // check the number of processors available
        System.out.println("" + Runtime.getRuntime()
                                    .availableProcessors());

    }
}
```

输出:

```java

```

**8) `public void exit(int status)`**
该方法通过启动当前运行的 Java 虚拟机的关机序列来终止当前运行的 Java 虚拟机。

```java
// Java program to illustrate exit()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // cause the program to exit
        Runtime.getRuntime().exit(0);

        //Nothing will run now.
        System.out.println("Program Running Check");
    }
}
```

输出:

```java
No Output
```

**9) `public void traceInstructions(boolean on)`**
此方法启用或禁用指令跟踪。如果布尔参数为 `true`，则表明 JVM (Java 虚拟机)在执行时会为虚拟机中的每条指令发出调试信息。

```java
// Java program to illustrate traceInstructions()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // start tracing for instructions
        Runtime.getRuntime().traceInstructions(true);

        System.out.println("Enabled");
        Runtime.getRuntime().traceInstructions(false);
        System.out.println("Disabled");

    }
}
```

输出:

```java
Enabled
Disabled
```

**10) `public void traceMethodCalls(boolean on)`**
此方法启用或禁用对方法调用的跟踪。如果布尔参数为 `true`，那么它将建议 Java 虚拟机在调用时为虚拟机中的每个方法发出调试信息。

```java
// Java program to illustrate traceMethodCalls()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
      // start tracing for instructions
      System.out.println("Enabling..");

      Runtime.getRuntime().traceMethodCalls(true);
      System.out.println("Enabled");
    }
}
```

输出:

```java
Enabling..
Enabled
```

**11) `public void loadLibrary(String libname)`**
这个方法用指定的库名加载动态库。包含代码的文件从通常获取库文件的地方从本地系统加载。

**异常:**
- `UnsatisfiedLinkError`: 如果库不存在。
- `NullPointerException`: 如果 `libname` 为 `null`。
- `SecurityException`: 如果 `checkLink` 方法不允许加载指定的动态库。

```java
// Java program to illustrate loadLibrary()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // load a library that is home/saket/Desktop folder
        Runtime.getRuntime().loadLibrary("/home/saket/Desktop/Library");

        System.out.println("Library Loaded Successfully");
    }
}
```

输出:

```java
Library Loaded Successfully
```

**12) `public void load(String filename)`**
此方法将指定的文件名加载为动态库。`filename` 参数必须是完整的路径名。

**异常:**
- `UnsatisfiedLinkError`: 如果库不存在。
- `NullPointerException`: 如果 `filename` 为 `null`。
- `SecurityException`: 如果 `checkLink` 方法不允许加载指定的动态库。

```java
// Java program to illustrate load()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // load a library that is home/saket/Desktop folder
        Runtime.getRuntime().loadLibrary("/home/saket/Desktop/File");

        System.out.println("Library Loaded Successfully");
    }
}
```

输出:

```java
Library Loaded Successfully
```

**13) `public void gc()`**
这个方法运行垃圾收集器。调用此方法建议 Java 虚拟机将精力扩展到回收未使用的对象，以便使它们当前占用的内存可用于快速重用。

# Java Runtime 类方法详解

## 14) `public void runFinalization()`
此方法运行任何等待终结的对象的终结方法。它建议 JVM (Java 虚拟机) 努力运行那些已经被发现被丢弃但其终结方法尚未运行的对象的终结方法。

```java
// Java program to illustrate runFinalization()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // run the finalization
        Runtime.getRuntime().runFinalization();

        System.out.println("Finalized");
    }
}
```

输出:
```java
Finalized
```

## 15) `public long maxMemory()`
此方法返回 Java 虚拟机将尝试使用的最大内存量。如果没有内在的限制，那么值为 `Long.MAX_VALUE`。

```java
// Java program to illustrate maxMemory()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // print the maximum memory
        System.out.println("" + Runtime.getRuntime().maxMemory());
    }
}
```

输出:
```java

```

## 16) `public void halt(int status)`
此方法强制终止当前运行的 Java 虚拟机。此方法从不正常返回。使用这种方法应该非常小心。

**异常:**
- **`SecurityException`:** 如果安全管理器存在并且其 `checkExit` 方法不允许以指定状态退出。

```java
// Java program to illustrate halt()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        // halt this process
        Runtime.getRuntime().halt(0);

        // print a string, just to see if it process is halted
        System.out.println("Process is still running.");
    }
}
```

输出:
```java
No Output
```

## 17) `public Process exec(String[] cmd)`
此方法在单独的进程中执行指定的命令和参数。这是一个方便的方法。

**异常:**
1. **`IndexOutOfBoundsException`:** 如果 `cmd` 为空数组(长度为 0)。
2. **`NullPointerException`:** 如果 `cmd` 为 `null`。
3. **`SecurityException`:** 如果安全管理器存在并且其 `checkExec` 方法不允许创建子进程。
4. **`IOException`:** 如果发生输入/输出错误。

```java
// Java program to illustrate exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            String[] cmd = new String[2];
            cmd[0] = "atom";
            cmd[1] = "File.java";
            // create a process and execute cmdArray
            Process process = Runtime.getRuntime().exec(cmd);

            // print another message
            System.out.println("File.java opening in atom");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:
```java
File.java opening in atom
```

## 18) `public Process exec(String command, String[] envp, File dir)`
此方法在具有指定环境和工作目录的单独进程中执行指定的 `String` 命令。这是一个方便的方法。

**异常:**
1. **`IndexOutOfBoundsException`:** 如果 `command` 为空。
2. **`NullPointerException`:** 如果 `command` 为 `null`，或 `envp` 的某个元素为 `null`。
3. **`SecurityException`:** 如果安全管理器存在并且其 `checkExec` 方法不允许创建子进程。
4. **`IOException`:** 如果发生输入/输出错误。

```java
// Java program to illustrate exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            // create a file with the working directory we wish
            File f = new File("/home/saket/Desktop");

            // create a process and execute gedit and current environment
            Process process = Runtime.getRuntime().exec("gedit", null, f);
            System.out.println("Gedit opening.");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:
```java
Gedit opening.
```

## 19) `public Process exec(String command, String[] envp)`
此方法在具有指定环境的单独进程中执行指定的 `String` 命令。这是一种方便的方法，其行为方式与调用 `exec(command, envp, null)` 完全相同。

**异常:**
1. **`NullPointerException`:** 如果 `command` 为 `null`，或 `envp` 的某个元素为 `null`。
2. **`SecurityException`:** 如果安全管理器存在并且其 `checkExec` 方法不允许创建子进程。
3. **`IOException`:** 如果发生输入/输出错误。

```java
// Java program to illustrate exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            // create a file with the working directory we wish
            File f = new File("/home/saket/Desktop");

            // create a process and execute gedit and current environment
            Process process = Runtime.getRuntime().exec("gedit", null);
            System.out.println("Gedit opening.");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:
```java
Gedit opening.
```

## 20) `public Process exec(String[] cmdarray, String[] envp, File dir)`
此方法在具有指定环境和工作目录的单独进程中执行指定的命令和参数。给定一个表示命令行标记的字符串数组 `cmdarray` 和一个表示“环境”变量设置的字符串数组 `envp`，这个方法创建一个执行指定命令的新进程。

**异常:**
1. **`IndexOutOfBoundsException`:** 如果 `cmdarray` 为空数组(长度为 0)。
2. **`NullPointerException`:** 如果 `cmdarray` 为 `null`，或 `envp` 的某个元素为 `null`。
3. **`SecurityException`:** 如果安全管理器存在并且其 `checkExec` 方法不允许创建子进程。
4. **`IOException`:** 如果发生输入/输出错误。

```java
// Java program to illustrate exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            String[] cmd = new String[2];
            cmd[0] = "atom";
            cmd[1] = "File.java";
            // create a file with the working directory we wish
            File dir = new File("/home/saket/Desktop");
            // create a process and execute cmdArray
            Process process = Runtime.getRuntime().exec(cmd, null, dir);
            System.out.println("File.java opening.");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:
```java
File.java opening.
```

## 21) `public Process exec(String[] cmdarray, String[] envp)`
此方法在具有指定环境的单独进程中执行指定的命令和参数。这是一个方便的方法。对 `exec(cmdarray, envp)` 的调用与对 `exec(cmdarray, envp, null)` 的调用行为完全相同。

**异常:**
1. **`IndexOutOfBoundsException`:** 如果 `cmdarray` 为空数组(长度为 0)。
2. **`NullPointerException`:** 如果 `cmdarray` 为 `null`，或 `envp` 的某个元素为 `null`。
3. **`SecurityException`:** 如果安全管理器存在并且其 `checkExec` 方法不允许创建子进程。
4. **`IOException`:** 如果发生输入/输出错误。

```java
// Java program to illustrate exec()
// method of Runtime class
public class GFG
{
    public static void main(String[] args)
    {
        try
        {
            String[] cmd = new String[2];
            cmd[0] = "atom";
            cmd[1] = "File.java";
            // create a file with the working directory we wish
            File dir = new File("/home/saket/Desktop");
            // create a process and execute cmdArray
            Process process = Runtime.getRuntime().exec(cmd, null);
            System.out.println("File.java opening.");
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

输出:
```java
File.java opening.
```

**参考文献:**
[https://docs.oracle.com/javase/7/docs/api/java/lang/Runtime.html](https://docs.oracle.com/javase/7/docs/api/java/lang/Runtime.html)

本文由 [**Saket Kumar**](https://www.facebook.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。