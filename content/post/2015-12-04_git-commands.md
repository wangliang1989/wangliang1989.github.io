---
title: "git 常用命令"
date: 2015-12-04T12:13:19+08:00
lastmod: 2015-12-04T12:13:19+08:00
draft: false
tags: ["git"]
categories: ["编程"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
slug: git-commands
---

# 和提交有关

添加或修改文件的修改提交到暂存区(记住：git跟踪的是修改！)

```bash
git add <fileName>
```

删除文件的修改提交到暂存区

```bash
git rm <fileName>
```

提交到仓库

```bash
git commit -m"<提交理由>"
```

将工作目录中已经跟踪的文件直接提交到仓库

```bash
git commit -a
```

# 和撤销有关

撤销工作目录的修改

```bash
git checkout -- <fileName>
```

撤销到暂存区的提交

```bash
git reset HEAD <fileName>
```

版本库回退,修改放回工作区

```bash
git reset HEAD~1
```

版本库回退,修改不放回工作区

```bash
git reset --hard HEAD~1
```

命令撤销

```bash
git reflog
git reset --hard <commit_ID>
```

# 和变基提交有关

手动变基

```bash
git rebase -i master
```

自动变基

```bash
git rebase master
```

# 和远程库有关

删除远程库

```bash
git push origin --delete <branchName>
```

# 关于 zsh

停用 zsh的 git-prompt 插件

```bash
git config --global oh-my-zsh.hide-status 1 #全局
git config oh-my-zsh.hide-status 1 # 当前 repo
```
