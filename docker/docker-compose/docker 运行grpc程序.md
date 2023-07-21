查看已运行容器，
```docker
docker ps
```

找到存放client.py代码的容器

查看容器挂载目录：
```docker
docker inspect 容器id
```
	“Source”：宿主机目录，
	"Destination"：容器目录
	"Mounts:[ ] "里面的
		"Source": "/home/yd/label_system",
		"Destination": "/apps",

进入容器找到client.py 或者 在宿主机里找到容器对应的挂载目录下的client.py
进入容器：
```docker
docker exec -it 容器id /bin/bash
```

vi 编辑器修改正确的HOST，wq保存退出
```docker
vi client.py
```

退出容器
```
exit
```

重启存放client.py代码的 容器，因为修改过，重启才能有用
```docker
docker restart 容器id
```

找到存放服务器端代码(ComputeServicer.py)的容器：92ffe0d10cbf   grpc/flask:cpu
查看容器挂载目录：
```docker
docker inspect 容器id
```

进入容器找到服务端(ComputeServicer.py)代码，后台运行
（运行容器的ComputeServicer.py，运行挂载目录的ComputeServicer.py会报错）
```docker
nohup python3 ComputeServicer.py &
```

查看所有进程，
```
ps aux
```
查看指定进程，python程序是否运行成功
```
ps aux | grep 进程名（只要名字中包含的都会显示出来）
```



```
（容器挂载目录：宿主机：/flask：容器：/yd）
进入容器，docker exec -it 92ffe0d10cbf /bin/bash
找到服务端代码（client.py）目录：/yd/client.py，
	
修改正确HOST（192.168.100.98），
	重启容器(restart)，
	
容器里修改过，宿主机挂载目录下的代码也会做相同改变
（宿主机：cd 到flask目录下修改），
因为已经挂载，修改一边，两边都会改变
	
	
cd /flask
后台运行python程序（ComputeServicer.py）：
nohup python3 ComputeServicer.py &
查看进程（正在运行的程序）：ps aux
````