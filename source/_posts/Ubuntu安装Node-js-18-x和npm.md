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
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
NODE_MAJOR=18 # 16 18 20
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.
sudo apt-get update
```

**2.安装Node.js和npm**

```bash
sudo apt-get install nodejs -y
```

**3.验证安装**

```bash
node -v
npm -v
```



## 卸载方法

```bash
apt-get purge nodejs &&\
rm -r /etc/apt/sources.list.d/nodesource.list &&\
rm -r /etc/apt/keyrings/nodesource.gpg
```



