---
title: Ubuntu安装Node.js 18.x和npm
date: 2023-08-22 10:08:00
tags:
- Ubuntu
- npm
- Node.js
categories:
- Node.js
---



## Ubuntu安装Node.js 18.x和npm

**1. 添加NodeSource的APT存储库**

```bash
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

**2.安装Node.js和npm**

```bash
sudo apt-get install nodejs
```

**3.验证安装**

```bash
node -v
npm -v
```

