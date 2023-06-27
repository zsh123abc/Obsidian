启动停止的容器：
```bash
docker start
```
kill 容器
```shell
docker kill 容器ID/容器名
```
停止容器
```shell
docker stop 容器ID/容器名
```
重启容器：
```shell
docker restart 容器ID/容器名
```
删除一个容器
docker rm -f 容器名/容器ID
删除多个容器 空格隔开要删除的容器名或容器ID
docker rm -f 容器名/容器ID 容器名/容器ID 容器名/容器ID
删除全部容器
docker rm -f $(docker ps -aq)

查看容器日志
```
docker logs -f -t --tail=100 5a9000a0cf6a
```

查看所有网络
```bash
docker network ls
```

查看指定网络的详细信息
```
docker nekwork inspect 网络名字NAME
```

发生容器启动不了之类的错误
查看最近30分钟的容器日志
Docker logs 命令——查看docker容器日志：
https://blog.csdn.net/weixin_39506322/article/details/119776737
```
docker logs --since 30m 容器id
```



查看容器完整信息：
```
docker ps -a --no-trunc
```

进入容器：docker attach 92ffe0d10cbf  （不用）
进入容器 ：
```
docker exec -it 容器id /bin/bash
```

容器：
	grpc/flask:cpu ：id：92ffe0d10cbf
	cncowboy/label-system-backend-python:v1.0 ：id：8d2c83c77b83

更换容器名
```
docker rename 容器ID/容器名 新容器名
```
重启容器：
```
docker restart 容器id
```


获取容器/镜像的元数据。
```
docker inspect 容器id
```
模版指令
	{{ }} 语法用于处理模版指令，大括号外的任何字符都将直接输出。
查看指定容器的ip地址
	“.” 表示“当前上下文”，大多数情况下表示了容器元数据的整个数据结构
```shell
ocker inspect -f {{.Config.Hostname}} 容器名或容器id
```
根据容器名查看容器id
```shell
docker inspect -f {{.Config.Hostname}} 容器名
```

提交一个镜像
```
docker commit -m="提交信息" -a="作者信息" 容器名/容器ID 提交后的镜像名:Tag
```


后台运行python程序( &标志后台运行)：
```
nohup python3 ComputeServicer.py &
```

查看docker-compose.yml所在位置
```
locate docker-compose.yml
```



cd /home/yd/label_system/flask/python_restful_file_system/file


docker-compose.yml文件路径：
	/home/yd/label_system/docker-compose.yml

挂载目录：
	cncowboy/label-system-backend-python:v1.0：
	挂载目录：
		宿主机：/home/yd/label_system
		容器：/apps
	
	grpc/flask:cpu ：
	挂载目录：
		宿主机：/flask
		容器：/yd


    command: /bin/bash -c "cd /flask/; nohup python3 ComputeServicer.py &; tail -f /dev/null"


volumes:
      - "/home/yd/flask:/yd"
    command: /ibin/bash -c "cd /yd/ && nohup python3 ComputeServicer.py &"





