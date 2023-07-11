---
title: ssh远程命令
date: 2023-07-04 16:45:41
tags:
- linux
---

前端本地打包推送远程服务器：
<!-- more-->
```bash
publish_dir=xxxx

rm -rf dist
npm run build
cd dist 
zip -r dist.zip *
scp -P xxxx dist.zip root@xx.xxx.xxx.xx:~
ssh -tt root@xx.xxx.xxx.xx -p xxxx << EOF 
cd $publish_dir
unzip -o -d $publish_dir ~/dist.zip
exit
EOF
```





ssh 远程命令参数:

```bash
-1：强制使用ssh协议版本1；
-2：强制使用ssh协议版本2；
-4：强制使用IPv4地址；
-6：强制使用IPv6地址；
-A：开启认证代理连接转发功能；
-a：关闭认证代理连接转发功能；
-b：使用本机指定地址作为对应连接的源ip地址；
-C：请求压缩所有数据；
-F：指定ssh指令的配置文件；
-f：后台执行ssh指令；
-g：允许远程主机连接主机的转发端口；
-i：指定身份文件；
-l：指定连接远程服务器登录用户名；
-N：不执行远程指令；
-o：指定配置选项；
-p：指定远程服务器上的端口；
-q：静默模式；
-X：开启X11转发功能；
-x：关闭X11转发功能；
-y：开启信任X11转发功能。
-n：表示只连接远程主机，不打开远程shell；
-t：表示不为这个连接分配TTY
```

