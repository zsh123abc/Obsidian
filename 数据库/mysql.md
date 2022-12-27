登录密码：123456

进入mysql的bin目录

```javascript
cd D:\zsh\mysql\mysql-8.0.31-winx64\bin
```

在MySQL目录下的bin目录下执行命令：

```bash
mysqld --initialize --console
```
**安装mysql服务**

```bash
mysqld --install mysql
```
**启动mysql服务**

```bash
net start mysql
```
**连接mysql**

```bash
mysql -uroot -p
```

进入mysql输入以下命令修改密码(把新的密码修改成你想要的密码)

```bash
ALTER USER 'root'@'localhost' IDENTIFIED BY '新的密码';
```



Mysqlworkbench汉化步骤
https://blog.csdn.net/weixin_51647998/article/details/126009505

mysql的基本操作
https://blog.csdn.net/weixin_45851945/article/details/114287877

mysql导入数据的方法
https://huaweicloud.csdn.net/63355048d3efff3090b53fb5.html