scp传输时不能有中文，中文会乱码
-r 传输整个文件夹
-p 传输时保留文件的属性和权限
将本地A主机文件复制到B主机： A:10.10.158.214 B：10.10.158.86
```c#
scp -p ./files/yum.log 10.10.158.86:/tmp/demo/
```
将远程主机复制到本地
```c#
scp -p 10.10.158.86:/tmp/demo/f3.log /tmp/files/
```
复制目录
```c#
scp -rp ./files/ 10.10.158.86:/tmp/demo
```
复制目录但是不包括顶级文件夹  /.
```
scp -r source_directory/. user@remote_host:destination_directory/
```

Windows上传下载文件到Linux
https://blog.csdn.net/m0_66757371/article/details/125827551