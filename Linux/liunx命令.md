linux配置ip
```
vi /etc/resolv.conf  192.168.100.254
```

立刻关机
-r 立刻重启
```
shutdown -h now
```

查看所有进程
```
ps aux
```
将1递归复制给2 
```
cp  -r 文件夹1 文件夹2 
```
移动文件夹
```
mv 
```
mv 同目录同名文件，可修改文件名字

删除
```
rm 删除文件
rm -f 不用确定直接删除
rm -rf 删除目录
```

查看文件类型
```
file
```
linux清屏命令
```
clear
```
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
ls | wc -l
```


只打印日志中最后一行匹配字符和后10位字符
```
cat solid_ball.log |grep -o  -P 'eta.{0,10}' -A 1 | tail -n 1
```

持续查看日志，有新的就会显示
```ssh
tail -f outside_court.log
```

查看GPU内存使用情况
```
nvidia-smi
```

ffmpeg翻转视频
```
ffmpeg -i out_court5.mp4 -vf "hflip" fz_out_court5.mp4
```


Ubuntu禁止自动更新ip
https://blog.csdn.net/u010571709/article/details/127221169

Linux上传文件没有权限，添加文件权限命令：
https://blog.csdn.net/ABCAA1024/article/details/125678677

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

zip 压缩命令
https://blog.csdn.net/MssGuo/article/details/117324818

解压unzip用法
https://blog.csdn.net/qq_35399846/article/details/70168002

Linux查看文件夹大小和文件大小的几种方法
https://blog.csdn.net/weixin_41287260/article/details/105281631


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


chatgpt国内永久网址
https://chat86.co/767837
https://chat2.jinshutuan.com/#/chat/1688096300542


wget下载太慢
下载mwget，先安装或更新组件：
```
sudo apt install build-essential
sudo apt upgrade intltool
sudo apt install  libssl-dev
```

```
wget http://jaist.dl.sourceforge.net/project/kmphpfm/mwget/0.1/mwget_0.1.0.orig.tar.bz2
tar -xjvf mwget_0.1.0.orig.tar.bz2
cd mwget_0.1.0.orig
./configure
sudo make
sudo make install
```
https://blog.csdn.net/Tang_Zhe/article/details/122668166


查找文件夹下的图片数量
```
find /path/to/directory -type f \( -iname "*.jpg" -o -iname "*.png" -o -iname "*.gif" \)
```
