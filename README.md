一键脚本安装shadowsocks/shadowsocksR/V2Ray + 开启bbr
---

一键脚本搭建shadowsocks/shadowsocksR/V2Ray + 设置开启自启动 + 升级内核&开启bbr加速。

## 教程如何访问
因为这个脚本，[flyzy小站](https://www.flyzy2005.com)已经被GFW拉入黑名单了，直接DNS污染了，国内无法访问。

如果有翻墙方法，自然可以直接访问（目前flyzy2005.com已加入GFWList）。如果还在墙内，可以参考[flyzy小站最新访问方式与镜像网站地址](https://flyzyblog.com/way-to-flyzy2005/)访问教程，科学上网吧！

## 支持系统
CentOS 6+

Debian 7+

Ubuntu 12+

## 使用教程
一键搭建ss/ssr：[一键脚本搭建shadowsocks+开启bbr](https://www.flyzy2005.com/fan-qiang/shadowsocks/install-shadowsocks-in-one-command/)

一键搭建V2Ray：[一键脚本搭建V2Ray+配置与优化](https://www.flyzy2005.com/v2ray/how-to-build-v2ray/)

或者参考：[Wiki](https://github.com/flyzy2005/ss-fly/wiki)

## 交流群
flyzy小站交流群：http://t.me/flyzyxiaozhan

搬瓦工用户交流群：https://t.me/banwagongusers

## 推荐的VPS
### 国外VPS
[Vultr优惠网](https://www.vultryhw.cn/)

[搬瓦工优惠网](https://www.bwgyhw.cn/)

### 国内VPS
[阿里云优惠网](https://www.aliyunyhw.com)

[腾讯云优惠网](https://www.tengxunyunyhw.com)

### VPS信息汇总
[VPS GO](https://www.vpsgo.com)



1.下载一键搭建ss脚本文件（直接在绿色光标处复制该行命令回车即可，只需要执行一次，卸载ss后也不需要重新下载）

git clone -b master https://github.com/flyzy2005/ss-fly
下载脚本

如果提示bash: git: command not found，则先安装git（你如果不知道自己是哪个系统，那就全部执行一次，然后再执行上面的那个下载命令）：

Centos系统执行这个： yum -y install git
Ubuntu/Debian系统执行这个： apt-get -y install git
2.运行搭建ss脚本代码

ss-fly/ss-fly.sh -i flyzy2005.com 1024
其中flyzy2005.com换成你要设置的shadowsocks的密码即可（这个flyzy2005.com就是你ss的密码了，是需要填在客户端的密码那一栏的），密码随便设置，最好只包含字母+数字，一些特殊字符可能会导致冲突。而第二个参数1024是端口号，也可以不加，不加默认是1024~（举个例子，脚本命令可以是ss-fly/ss-fly.sh -i qwerasd，也可以是ss-fly/ss-fly.sh -i qwerasd 8585，后者指定了服务器端口为8585，前者则是默认的端口号1024，两个命令设置的ss密码都是qwerasd）：

ss安装

界面如下就表示一键搭建ss成功了：

ssr安装成功

注：如果需要改密码或者改端口，只需要重新再执行一次搭建ss脚本代码就可以了，或者修改/etc/shadowsocks.json这个配置文件（如何修改在公众号回复vim编辑器使用）。

3.相关ss操作

修改配置文件：vim /etc/shadowsocks.json
停止ss服务：ssserver -c /etc/shadowsocks.json -d stop
启动ss服务：ssserver -c /etc/shadowsocks.json -d start
重启ss服务：ssserver -c /etc/shadowsocks.json -d restart
4.卸载ss服务

ss-fly/ss-fly.sh -uninstall
