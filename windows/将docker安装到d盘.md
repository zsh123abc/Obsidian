docker不能更改安装路径

docker desktop下载网站
https://www.docker.com/get-started/

先卸载docker
已管理员身份运行cmd
在d盘下对应目录下创建文件夹
软连接，把c盘下文件映射到d盘，c盘的文件只是一个目录，真正的文件在d盘下面
```
mklink /j "C:\Program Files\Docker" "D:\Program Files\Docker"
```
成功显示：
```
为 C:\Program Files\Docker <<===>> D:\Program Files\Docker 创建的联接
```
重新安装docker

打开界面设置，
Settings -> Resources -> Advanced -> Disk image location
修改到d盘

设置完，安装位置和镜像存放位置都在d盘

https://blog.csdn.net/liangcsdn111/article/details/110236655

彻底解决win10 docker desktop镜像过大导致“C盘存储空间不足”的问题。
https://www.codenong.com/cs110392568/