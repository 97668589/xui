# XUI-一个多用户xray面板
原版x-ui安装脚本:最新加入s390x架构支持
```
bash <(curl -Ls https://raw.githubusercontent.com/97668589/xui/master/install.sh) 
```
# 手动安装&升级

首先从https://github.com/vaxilu/x-ui/releases下载最新的压缩包，一般选择amd64架构
然后将这个压缩包上传到服务器的/root/目录下，并使用root用户登录服务器
如果你的服务器cpu架构不是amd64，自己将命令中的amd64替换为其他架构
```
cd /root/
rm x-ui/ /usr/local/x-ui/ /usr/bin/x-ui -rf
tar zxvf x-ui-linux-amd64.tar.gz
chmod +x x-ui/x-ui x-ui/bin/xray-linux-* x-ui/x-ui.sh
cp x-ui/x-ui.sh /usr/bin/x-ui
cp -f x-ui/x-ui.service /etc/systemd/system/
mv x-ui/ /usr/local/
systemctl daemon-reload
systemctl enable x-ui
systemctl restart x-ui
```
