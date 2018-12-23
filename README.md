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

## 按照提示进行访问