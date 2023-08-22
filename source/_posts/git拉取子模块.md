---
title: git拉取子模块
date: 2023-08-22 10:07:35
tags:
- git
- submodule
- 子模块
categories:
- git
---



## git子模块



### 1. clone时一起拉取子模块

```bash
git clone --recurse-submodules <父仓库地址>
```



### 2. 单独拉取子模块

```bash
cd <父仓库路径>
git submodule init #初始化子模块
git submodule update # 更新子模块与主仓库中的子模块代码同步
```

或

```bash
cd <父仓库路径>
git submodule update --init
```



### 3.如果子模块中包含子模块

```bash
git submodule update --init --recursive
```

