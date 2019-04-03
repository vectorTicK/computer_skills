# 安装配置ubuntu18.04
1. 进入按照启动画面后选择ubuntu install,按‘e’键，添加：nomodeset
1. 重启后选择ubuntu，按‘e’键，添加：nomodeset
1. 进入系统后开启无线网卡：
```
sudo gedit /etc/modprob.d/ideapad.conf
blacklist ideapad_laptop
sudo touch /etc/modprobe.d/ideapad.conf
sudo modprobe -r ideapad_laptop
```
4. 连接网络后更新软件
update software
5. 安装显卡驱动：
```
nvidia drivers:ubuntu-drivers devices, sudo ubuntu-drivers autoinstall
```
6. 按照ubuntu tweak、gnomeshell插件 

可以正常使用了，需要什么软件搜索就可以了