# Java 中的 Java.lang.Process 类

> 原文：[https://www.geeksforgeeks.org/java-lang-process-class-java/](https://www.geeksforgeeks.org/java-lang-process-class-java/)

抽象的`Process`类代表一个进程——也就是一个正在执行的程序。`Process`提供的方法用于输入、输出、等待流程完成、检查流程退出状态和销毁流程。

*   它扩展了类`Object`。
*   它主要用作`Runtime`类中`exec()`创建的对象类型的超类。
*   `ProcessBuilder.start()`和`Runtime.getRuntime().exec()`方法创建一个本机进程，并返回一个`Process`子类的实例，该实例可用于控制该进程并获取有关该进程的信息。
*   `ProcessBuilder.start()`是创建流程的最首选方式。

**ProcessBuilder.start() vs. Runtime.getRuntime().exec():** `ProcessBuilder`允许我们将子进程的标准错误重定向到其标准输出中。现在我们不需要两个单独的线程一个从`stdout`读取，一个从`stderr`读取。

## 构造方法

*   `Process()`: 这是唯一的构造方法。

## 方法

### `void destroy()`

杀死子进程。

```java
Syntax: public abstract void destroy().
Returns: NA.
Exception: NA.
```

```java
// Java code illustrating destroy() 
// method for windows operating system
public class ProcessDemo 
    public static void main(String[] args) 
    {
        try 
        {
            // create a new process
            System.out.println("Creating Process");
            ProcessBuilder builder = new ProcessBuilder("notepad.exe");
            Process pro = builder.start();

            // wait 10 seconds
            System.out.println("Waiting");
            Thread.sleep(10000);

            // kill the process
            pro.destroy();
            System.out.println("Process destroyed");
        } 
        catch (Exception ex) 
        {
            ex.printStackTrace();
        }
    }
}
```

输出：

```java
Creating Process
Waiting
Process destroyed
```

```java
// Java code illustrating destroy()
// method for Mac Operating System
import java.lang.*;
import java.io.*;
class ProcessDemo
{
    public static void main(String arg[]) throws IOException, Exception
    {
        System.out.println("Creating process");
        //creating process
        ProcessBuilder p = new ProcessBuilder(new String[] 
                        {"open", "/Applications/Facetime.app"});
        Process pro = p.start();

        //waiting for 10 second
        Thread.sleep(10000);
        System.out.println("destroying process");
        //destroying process
        pro.destroy();
    }
}
```

输出：

```java
Creating process
destroying process
```

### `int exitValue()`

此方法返回子进程的退出值。

```java
Syntax: public abstract int exitValue().
Returns: This method returns the exit value of 
the subprocess represented by this Process object. 
By convention, the value 0 indicates normal termination.
Exception: IllegalThreadStateException ,
if the subprocess represented by this Process object has not yet terminated.
```

```java
// Java code illustrating exitValue() method
public class ProcessDemo 
{
    public static void main(String[] args)
    {
        try 
        {
            // create a new process
            System.out.println("Creating Process");
            ProcessBuilder builder = new ProcessBuilder("notepad.exe");
            Process pro = builder.start();

            // kill the process
            pro.destroy();

            // checking the exit value of subprocess
            System.out.println("exit value: " + pro.exitValue());
        } 
        catch (Exception ex) 
        {
            ex.printStackTrace();
        }
    }
}
```

输出：

```java
Creating Process
```

### `abstract InputStream getErrorStream()`

此方法获取子进程的错误流。

```java
Syntax: public abstract InputStream getErrorStream().
Returns: input stream that reads input from the process error stream.
Exception: NA.
```

```java
// Java code illustrating
// getErrorStream() method
import java.lang.*;
import java.io.*;
class ProcessDemo
{
    public static void main(String arg[]) throws IOException, Exception
    {
        // creating the process
        Runtime r = Runtime.getRuntime();
```

// shell script for loop from 1 to 3
```java
String[] nargs = {"sh", "-c", "for i in 1 2 3; do echo $i; done"};
Process p = r.exec(nargs);

BufferedReader is = new BufferedReader(new InputStreamReader(p.getInputStream()));
String line;

// reading the output
while ((line = is.readLine()) != null)
    System.out.println(line);
}
}
```

输出:

```java

```

## `abstract OutputStream getOutputStream()`

此方法获取子进程的输出流。输出到该流的数据会被输送到由此 `Process` 对象表示的进程的标准输入流。

```java
Syntax: public abstract OutputStream getOutputStream()
Returns: the output stream connected to the normal input of the subprocess.
Exception: NA.
```

```java
// Java code illustrating getOutputStream() method
import java.io.BufferedOutputStream;
import java.io.OutputStream;

public class ProcessDemo {
    public static void main(String[] args) {
        try {
            // create a new process
            System.out.println("Creating Process");
            Process p = Runtime.getRuntime().exec("notepad.exe");

            // get the output stream
            OutputStream out = p.getOutputStream();

            // close the output stream
            System.out.println("Closing the output stream");
            out.close();
        } catch (Exception ex) {
            ex.printStackTrace();
        }
    }
}
```

输出:

```java
Creating Process...
Closing the output stream...
```

## `abstract InputStream getErrorStream()`

它返回一个输入流，用于读取来自进程标准错误输出流的数据。

```java
Syntax: public abstract InputStream getErrorStream().
Returns: the input stream connected to the error stream of the subprocess.
Exception: NA.
```

```java
// Java code illustrating getErrorStream() method
import java.io.InputStream;

public class ProcessDemo {
    public static void main(String[] args) {
        try {
            // create a new process
            System.out.println("Creating Process");
            Process p = Runtime.getRuntime().exec("notepad.exe");

            // get the error stream of the process and print it
            InputStream error = p.getErrorStream();
            for (int i = 0; i < error.available(); i++) {
                System.out.println("" + error.read());
            }

            // wait for 10 seconds and then destroy the process
            Thread.sleep(10000);
            p.destroy();
        } catch (Exception ex) {
            ex.printStackTrace();
        }
    }
}
```

输出:

```java
Creating Process
```

## `int waitFor()`

返回进程返回的退出码。此方法会一直阻塞，直到调用它的进程终止。

```java
Syntax: public int waitFor().
Returns: the exit value of the process. By convention, 0 indicates normal termination.
Exception: throws InterruptedException.
```

```java
// Java code illustrating waitFor() method
public class ProcessDemo {
    public static void main(String[] args) {
        try {
            // create a new process
            System.out.println("Creating Process");
            Process p = Runtime.getRuntime().exec("notepad.exe");

            // cause this process to stop until process p is terminated
            p.waitFor();

            // when you manually close notepad.exe, program will continue here
            System.out.println("Waiting over");
        } catch (Exception ex) {
            ex.printStackTrace();
        }
    }
}
```

输出:

```java
Creating Process...
Waiting over.
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。