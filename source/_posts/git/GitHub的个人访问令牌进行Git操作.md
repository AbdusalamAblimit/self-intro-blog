---
title: 使用GitHub的个人访问令牌进行Git操作
date: 2023-08-22 10:09:12
tags:
- git
- github
- PAT
- 个人令牌
categories:
- git
---

## 使用GitHub的个人访问令牌进行Git操作

由于GitHub已经停止支持通过密码进行命令行访问，个人访问令牌成为了身份验证的推荐方式。以下是几种使用这些令牌的方法。

### 1. 命令行交互式输入

当你使用命令行克隆、拉取或推送到远程仓库时，会被要求提供用户名和“密码”。

- 用户名: 你的GitHub用户名。
- 密码: 使用你的Personal Access Token。

### 2. 修改远程仓库URL

通过将token直接包含在remote URL中，你可以避免每次进行远程操作时都输入token。

```
git remote set-url origin https://TOKEN@github.com/USERNAME/REPO_NAME.git
```

其中：

- `TOKEN`: 你的个人访问令牌。
- `USERNAME`: 你的GitHub用户名。
- `REPO_NAME`: 你的GitHub仓库名称。

> ⚠️ 警告: 使用这种方法可能会在某些git日志或配置文件中暴露你的token，确保不与他人共享，并只在信任的环境中使用此方法。

### 3. 使用Credential Helper

Credential helper允许你存储git凭据，这样你不需要每次操作时都输入它们。要设置git使用默认的credential helper进行存储，执行：

```
git config --global credential.helper store
```

但请注意，使用此命令会以明文形式存储token。对于更安全的存储，可以考虑使用其他credential helper。
