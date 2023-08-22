---
title: Ubuntu通过官方脚本安装docker
date: 2023-08-22 10:08:35
tags:
- Ubuntu
- Docker
categories:
- Docker
---

## Ubuntu通过官方脚本安装docker

**1.下载官方脚本并进行安装**

```bash
curl -fsSL get.docker.com -o get-docker.sh
sh get-docker.sh
```

**2.确保docker用户组成功创建**

```bash
if [ ! $(getent group docker) ];
then 
    sudo groupadd docker;
else
    echo "docker user group already exists"
fi
```

**3. 将当前用户添加到docker用户组里**

```bash
sudo gpasswd -a $USER docker
sudo service docker restart
```

**4. 删除脚本文件**

```bash
rm -rf get-docker.sh
```

---

安装后使用docker命令时可能仍然会提示权限不足，此时只要重启主机(如果是WSL，只需重启WSL)即可。
