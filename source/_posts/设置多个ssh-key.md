---
title: 电脑设置多个ssh key账户
date: 2023-06-23 18:42:55
categories: 
- 计算机
tags: 
- git
---

## SSH (Secure Shell Protocol)

​	一种加密的网络传输协议，可在不安全的网络中为网络服务提供安全的传输环境。SSH以非对称加密实现身份验证，生成一对公钥和私钥。把公钥放在需要访问的服务器上，客户端向服务器发出请求使用私钥证明自己的身份。`ssh-keygen`是生成密钥的工具之一。

## 配置SSH

1. **生成rsa密钥**

   `$ ssh-keygen -t rsa -C "xxxx@gmail.com" -f id_rsa_xxx`

   -t：指定创建密钥类型
   -C：添加注释
   -f：指定保存密钥的文件名	

2. **拷贝公钥到服务器**

   [github -> settings -> SSH keys]

   `$ cat id_rsa_xxx.pub*`



3. **ssh config setting**

文件位置： `$ ~/.ssh/config`

```bash
# github acc1
Host github1  // 昵称，和git@xxxxx:**/**.git 中的xxx 保持一致
HostName github.com // ssh连接过去的主机名。这里可以是ip
IdentityFile ~/.ssh/id_rsa_github_**  // 密钥文件路径
PreferredAuthentications publickey
User ***@gmail.com  // 登录主机的用户名

# github acc2
Host github2  // 昵称，和git@xxxxx:**/**.git 中的xxx 保持一致
HostName github.com
IdentityFile ~/.ssh/id_rsa_github_**
PreferredAuthentications publickey
User ***@gmail.com
```

