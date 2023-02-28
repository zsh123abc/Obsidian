远程调试

vscode远程调试python：
https://blog.csdn.net/weixin_43632687/article/details/124108274

在本地VSCode上远程调试云服务器上的Python项目：
https://dalewushuang.blog.csdn.net/article/details/118278116


1、VSCode下载插件
`Ctrl+Shift+X`搜索`remote development`，并安装。

2，打开git bash，输入：
```
# 生成公钥私钥对
ssh-keygen -t rsa
```

3，然后复制`C:\Users\cwj\.ssh\id_rsa.pub`中的内容，
并添加到服务器的`~/.ssh/authorized_keys` 中

4，在`C:\Users\cwj\.ssh\`新建config文件
	config配置：
```
	Host 192.168.100.98   （ip地址）
	    HostName 192.168.100.98   
	    User yd   （用户名）
	    ForwardAgent yes
	    IdentityFile C:\Users\84977\.ssh\id_rsa  （id_rsa存放路径）
```
5，1.  在linux修改.ssh目录和authorized_keys权限。
```bash
chmod 700 .ssh
chmod 600 .ssh/authorized_keys
```

6，在viscode中连接远程服务器

ctrl+f 文件内搜索


vscode全局批量添加引号（其他符合添加同理）
https://blog.csdn.net/qq_43783527/article/details/124466701