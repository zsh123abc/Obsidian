1.基于以有容器创建镜像:
```
docker commit -m "镜像说明" -a "作者" 容器id 目标镜名:标签名
```

2.基于本地模板镜像创建：
```
 cat 镜像模板 | docker import - zsh1234:v1
```

3.基于Dockerfile文件创建镜像：
```
docker build -t 镜像名字 .
```

docker从文件载入镜像
```bash
docker load -i 镜像文件
```
docker部署镜像三种方法
https://blog.csdn.net/weixin_45947267/article/details/108048324

Dockerfile参数详解
https://blog.csdn.net/zhong_jay/article/details/108668166

