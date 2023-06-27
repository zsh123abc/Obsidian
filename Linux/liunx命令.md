查看所有进程
```
ps aux
```
cp  -r 文件夹1 文件夹2 将1递归复制给2 
mv 移动文件夹
mv 同目录同名文件，可修改文件名字

rm 删除文件
rm -f 删除文件夹
rm -rf 删除目录

file 命令：查看文件类型

linux清屏命令
clear命令
这个命令将会刷新屏幕，本质上只是让终端显示页向后翻了-页,
如果向上滚动屏幕还可以看到之前的操作信息。

新建文件夹：mkdir
新建文件：touch
查找文件：locate

查看Linux系统版本信息
https://blog.csdn.net/lu_embedded/article/details/44350445
```
cat /etc/issue
```

统计行数
```
sudo parted -l | grep \/dev\/sd | wc -l
```


Linux上传文件没有权限，添加文件权限命令：
https://blog.csdn.net/ABCAA1024/article/details/125678677

 scp传输时不能有中文，中文会乱码

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


启动飞浆容器
```d
docker run -it  --gpus all  -v /mnt/6T01/PaddleDetection2.4.2:/PaddleDetection2.4.2  --name paddle-zsh2  paddlepaddle/paddle:2.4.2-gpu-cuda11.2-cudnn8.2-trt8.0 /bin/bash
```


python tools/train.py -c configs/picodet/solid_ball.yml --eval >solid_ball.log 2>&1&

Windows上传下载文件到Linux
scp -r 传输文件夹
https://blog.csdn.net/m0_66757371/article/details/125827551




centos下安装python3详细教程
https://blog.csdn.net/t8116189520/article/details/81976755

linux软连接-python软连接创建、删除、查看
https://blog.csdn.net/u011304078/article/details/121430785

centos下python2和python3的pip设置，区分pip2和pip3
https://blog.csdn.net/t8116189520/article/details/81977623

Docker 安装 CentOS7
https://blog.csdn.net/qq_38616723/article/details/125276545

PaddlePaddl安装
https://blog.csdn.net/stone_tomcate/article/details/98970567

python tools/train.py -c configs/picodet/picodet_s_320_coco_lcnet.yml --eval > .log 2>&1&


只打印日志中最后一行匹配字符和后10位字符
```
cat solid_ball.log |grep -o  -P 'eta.{0,10}' -A 1 | tail -n 1
```
eta: 7:39:10 


zip 压缩命令
https://blog.csdn.net/MssGuo/article/details/117324818

解压unzip用法
https://blog.csdn.net/qq_35399846/article/details/70168002

Linux查看文件夹大小和文件大小的几种方法
https://blog.csdn.net/weixin_41287260/article/details/105281631


持续查看日志，有新的就会显示
```ssh
tail -f outside_court.log
```

查看GPU内存使用情况
```
nvidia-smi
```


linux下载文件没有权限
```
chmod -R 777 PaddleDetection/
```
https://blog.csdn.net/wangxiaozhonga/article/details/125322413
chmod -R 755 PaddleDetection/
添加权限后文件夹背景显示绿色高亮
Linux下如何解决目录绿色高亮？
https://blog.csdn.net/nan_xiaobai/article/details/99108689


查看gpu信息
```
nvidia-smi
```

```
nvidia-smi -l 1
```
查看cuda版本
```
nvcc -V
```

远程服务器简略指南，
常用命令
https://blog.csdn.net/lly1122334/article/details/88667123

安装gpu显卡驱动
https://blog.csdn.net/a1633146782/article/details/122467251  

查看所有可登录用户
```
grep -E "/bin/bash|/bin/sh" /etc/passwd | cut -d: -f1
```



_Fliplr_,_Multiply_,_AddToHueAndSaturation_,_Mix_


https://chat86.co/767837

在文件名后缀前添加 `_gray`
```SH
for file in *; do mv -- "$file" "${file%.*}_gray.${file##*.}"; done
```


去除目录绿色背景的方法
```
echo "OTHER_WRITABLE 01;34" >> $HOME/.dir_colors
```

```
eval `dircolors $HOME/.dir_colors`
```

```
source ~/.bashrc
```

修改bash默认颜色方案时提示：dircolors: no SHELL environment variable, and no shell type option given

解决：在.bashrc中设置：export SHELL="bash"



Congratulations, Shadowsocks-libev server install completed!
Your Server IP        :  154.9.88.83 
Your Server Port      :  14963 
Your Password         :  yuedong888 
Your Encryption Method:  aes-256-gcm 

Welcome to visit:https://teddysun.com/357.html
Enjoy it