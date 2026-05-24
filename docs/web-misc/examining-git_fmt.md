# 检查 Git

> 原文: [https://www.geeksforgeeks.org/examining-git/](https://www.geeksforgeeks.org/examining-git/)

对存储库进行基本快照后，使用以下命令获取其提交历史记录。

*   `git log`
*   `git shortlog`
*   `git diff`

现在，我们将讨论每个命令及其不同的可用选项。

## git log

顾名思义，这个命令显示提交日志。这是一个命令，允许您查看关于上一次提交的信息。与 `git status` 命令不同，它只检查提交存储库的历史。

*   `git log --all` 或 `git log`：此命令显示所有提交。
*   `git log -n "limit"`：该选项通过应用限制来帮助过滤提交历史。用多个提交替换“限制”会将输出限制为 n 个最近提交的。
*   `git log --author="name"`：此选项将输出限制为由特定作者“name”提交。
*   `git log --committer="name"`：此选项将结果限制为该个人提交的提交。
*   `git log -p`：此选项显示最详细的历史视图。这里 p 代表补丁。
*   `git log --oneline`：此选项用于在每次提交时获取单行中的空白信息。
*   `git log --stat`：此选项有助于查看每次提交中所做更改的摘要。
*   `git log "file"`：该选项显示包含指定文件的提交。
*   `git log --before="date"` (或 `--after`)：这将提交限制在给定日期范围内。日期被指定为 `"yyyy-mm-dd"` 格式的字符串。
*   `git log --after="date" --before="date"`：此选项指定一个日期范围。

## git shortlog

该命令是 `git log` 的“子命令”，因为它汇总了 `git log` 输出。每个提交按作者和标题分组。

*   `git log -n --numbered`：它根据每个作者的提交次数显示输出。
*   `git log -s --summary`：此选项禁止提交描述。
*   `git log -e --email`：此选项显示每个作者的电子邮件地址。
*   `git log -c --committer`：此选项显示提交者身份，而不是作者。
*   `git log "revision range"`：显示指定修订范围内的提交。

## git diff

这个命令用于比较文件的不同版本，或者换句话说，它显示提交、工作树、分支、文件等之间的变化。

## 总结

我们了解到 `git log` 命令是一个基本工具，用于查看提交的历史。`git log` 是一个连续的提交记录。`git shortlog` 只是 `git log` 的一个子命令——汇总 `git log` 的输出。我们刚刚描述了 `git diff` 命令，它是 git 最高级的选项之一。