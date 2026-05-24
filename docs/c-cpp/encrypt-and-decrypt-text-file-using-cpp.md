# 使用 C++ 对文本文件进行加密和解密

> 原文:[https://www . geesforgeks . org/encrypt-and-decrypt-text-file-use-CPP/](https://www.geeksforgeeks.org/encrypt-and-decrypt-text-file-using-cpp/)

[加密](https://www.geeksforgeeks.org/difference-between-symmetric-and-asymmetric-key-encryption/)[密码学](https://www.geeksforgeeks.org/cryptography-and-its-types/)中的是一个过程，通过这个过程，一个纯文本或一条信息被转换成[密文](https://www.geeksforgeeks.org/transforming-a-plain-text-message-to-cipher-text/)或一个只能由信息的接收者解码的文本。用于加密过程的算法被称为[密码](https://www.geeksforgeeks.org/block-cipher-modes-of-operation/)。它有助于保护消费者信息、电子邮件和其他敏感数据免受未经授权的访问，并保护通信网络。目前有许多选择，并找到最安全的算法，满足我们的要求。

**解密:** [解密](https://www.geeksforgeeks.org/difference-between-encryption-and-decryption/)是将无意义的消息(密文)转换为原始形式(明文)的过程。它通过应用与用于加密数据的算法相反的转换算法来工作。将信息解密回其正常形式需要相同的密钥。

**密码学的类型:**密码学有两种类型:

*   **对称加密法:**它是一种加密系统，消息的发送方和接收方使用一个公共密钥来加密和解密消息。对称密钥系统更快更简单，但是发送方和接收方必须以某种方式安全地交换密钥。最流行的对称密钥加密系统是数据加密系统。
*   **非对称密码学:**在这个系统下，使用一对密钥对信息进行加密和解密。公钥用于加密，私钥用于解密。公钥和私钥是不同的。即使每个人都知道公钥，预期的接收者也只能解码它，因为只有他知道私钥。

在本文中，对称加密用于加密和解密数据。

**方法:**在进入实现部分之前，我们先详细讨论一下方法:

*   类 ***encdec*** 定义了两个成员函数:加密()和解密()。要加密的文件名是类的成员变量。
*   **encrypt()功能**用于处理输入文件的加密。文件处理代码包含在 encrypt()函数中，用于读取文件和写入文件。一个名为 *encrypt.txt* 的新加密文件被生成，其中包含所有加密数据。使用用户输入的密钥对加密文件进行加密。
*   **decrypt()函数**用于读取加密文件并解密数据，生成新文件 *decrypt.txt.* 要解密文件，需要用户提供密钥。如果输入了正确的密钥，则文件被成功解密。
*   输入流 [*fin*](https://www.geeksforgeeks.org/file-handling-c-classes/) 用于从文件中读取，输出流 [*fout*](https://www.geeksforgeeks.org/how-to-work-with-file-handling-in-c/) 用于写入文件。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
#include <fstream>
using namespace std;

// encdec class with encrypt() and
// decrypt() member functions
class encdec {
    int key;

    // File name to be encrypt
    string file = "geeksforgeeks.txt";
    char c;

public:
    void encrypt();
    void decrypt();
};

// Definition of encryption function
void encdec::encrypt()
{
    // Key to be used for encryption
    cout << "key: ";
    cin >> key;

    // Input stream
    fstream fin, fout;

    // Open input file
    // ios::binary- reading file
    // character by character
    fin.open(file, fstream::in);
    fout.open("encrypt.txt", fstream::out);

    // Reading original file till
    // end of file
    while (fin >> noskipws >> c) {
        int temp = (c + key);

        // Write temp as char in
        // output file
        fout << (char)temp;
    }

    // Closing both files
    fin.close();
    fout.close();
}

// Definition of decryption function
void encdec::decrypt()
{
    cout << "key: ";
    cin >> key;
    fstream fin;
    fstream fout;
    fin.open("encrypt.txt", fstream::in);
    fout.open("decrypt.txt", fstream::out);

    while (fin >> noskipws >> c) {

        // Remove the key from the
        // character
        int temp = (c - key);
        fout << (char)temp;
    }

    fin.close();
    fout.close();
}

// Driver Code
int main()
{
    encdec enc;
    char c;
    cout << "\n";
    cout << "Enter Your Choice : -> \n";
    cout << "1\. encrypt \n";
    cout << "2\. decrypt \n";
    cin >> c;
    cin.ignore();

    switch (c) {
    case '1': {
        enc.encrypt();
        break;
    }
    case '2': {
        enc.decrypt();
        break;
    }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-634669-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210628170518/20210628_170033.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210628170518/20210628_170033.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210628170518/20210628_170033.mp4)</video>