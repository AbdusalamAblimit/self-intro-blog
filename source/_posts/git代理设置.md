---
title: git代理设置
date: 2023-08-22 10:07:09
tags:
- git
- 代理
categories:
- git
---

## git设置代理

设置http代理：

```bash
git config --global http.proxy <ip>:<port>
```

设置https代理

```
git config --global https.proxy <ip>:<port>
```

取消代理:

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

检查代理设置

```
git config --global --get http.proxy
git config --global --get https.proxy
```

