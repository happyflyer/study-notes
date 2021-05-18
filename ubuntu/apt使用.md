# apt 使用

- [Ubuntu 镜像使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/)

## 1. 清华源

```bash
sudo mv /etc/apt/sources.list /etc/apt/sources.list.bak
```

```bash
sudo vim /etc/apt/sources.list
```

```yaml
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

```bash
sudo apt-get clean && apt-get update
```

## 2. 代理

- 临时

```bash
sudo apt-get install package_name -o Acquire::http::proxy="http://代理服务器IP:端口"
```

- 配置

```bash
vim /etc/apt/apt.conf
```

```bash
Acquire::http::Proxy "http://代理服务器IP:端口";
```

## 3. 中文支持

```bash
sudo apt-get install language-pack-zh-hans
```

## 4. 用户操作

```bash
sudo useradd -d /home/user -m -s /bin/bash user
sudo passwd user
```

```bash
sudo userdel -r user
```

```bash
sudo usermod -aG group user
```
