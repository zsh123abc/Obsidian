	Dockerfile是用来构建镜像的，若是想使用这个镜像的话还需要使用docker run命令来运行这个镜像，从而生成运行一个容器
	
	docker-compose.yml来定义一组相关联的应用容器为一个项目（project）。是用来编排项目的，里面包含使用各种镜像创建的容器服务，使用的镜像可以是网络上的，也可以是根据使用Dockerfile文件来生成的镜像，相当于是把上一步的这个工作给做了


https://blog.csdn.net/DDFFR/article/details/77049118

92ffe0d10cbf  grpc/flask:cpu
/yd/client.py

8d2c83c77b83  cncowboy/label-system-backend-python:v1.0
/apps/flask/python_restful_file_system/file/client.py