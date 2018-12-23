# bt_panel_docker_vlome
bt_panel_docker_vlome 宝塔Linux面板v6.8 /www 挂载目录

# 基础镜像

- tangcuyu/base_centos7

# 面板版本
- v6.8

# 安装方式
```bash
# yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && bash install.sh
```

# 使用方法

```bash
# git clone https://github.com/zzutcy/bt_panel_docker_vlome.git && cd bt_panel_docker_vlome/www

# docker run --privileged=true --cap-add SYS_ADMIN -e container=docker --name=bt_cn -p 80:80 -p 2222:2222 -p 443:443 -p 8888:8888 -p 888:888 -v ${PWD}:/www -d  --restart=always   tangcuyu/base_centos7  /usr/sbin/init

# docker exec -it bt_cn /bin/bash

# 容器
# bt
# 14
```

## 请使用正确的入口登录面板
错误原因：当前宝塔新安装的已经开启了安全入口登录，新装机器都会随机一个8位字符的安全入口名称，亦可以在面板设置处修改，如您没记录或不记得了，可以使用以下方式解决

解决方法：在SSH终端输入以下一种命令来解决

1.查看面板入口：/etc/init.d/bt default

2.关闭安全入口：rm -f /www/server/panel/data/admin_path.pl

注意：【关闭安全入口】将使您的面板登录地址被直接暴露在互联网上，非常危险，请谨慎操作

## 版本介绍

### V1.0 版本只是初始面板没有安装 组件环境

### V2.0 版本安装了 lnmp web服务器环境。

```bash
Nginx       1.15
Mysql       5.7
Pure-Ftpd   1.0.47
PHP         7.0
phpMyAdmin  4.7
```