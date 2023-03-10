创建一个pyhton脚本，里面导入flask框架使用
创建Dockerfile：
	Dockerfile文件内容：
	
		其指定一个构建镜像的基础源镜像
		FROM python:3.8
	
		用于指定 docker build 过程中要运行的命令
		RUN pip install flask
		
		当前目录
		WORKDIR /app
		
		复制本机文件或目录或远程文件，添加到指定的容器目录
		COPY app.py /app/
		
		CMD在Dockerfile中只能出现一次，有多个，只有最后一个会有效
		如果用户执行docker run的时候提供了命令项，就会覆盖掉这个命令。没提供就会使用构建时的命令
		CMD ["python","app.py"]


cd到flask项目主目录下开始build：
	docker build 命令用于使用 Dockerfile 创建镜像。
		docker build -t flaskdemo（镜像部署进docker后的名字） .
查看镜像：docker imager
启动容器：
```bash
docker run --name "container名称" -d -p 主机端口号:镜像端口号 image-name
```
docker run -d -p 127.0.0.1:6200:5000 --name mydemo1 flaskdemo
访问本机6200端口：localhost:6200


镜像部署到docker之后，python文件内容修改就需重新部署新的镜像

docker部署一个最简单的flask项目
https://blog.csdn.net/weixin_44867493/article/details/125620653

获取flask请求参数的几种方式：
https://wangandh.blog.csdn.net/article/details/115955818

python web--Flask工作流程：
https://blog.csdn.net/qq_29027865/article/details/116074802

docker入门:docker部署flask项目：
https://www.codenong.com/cs106953688/

用Docker部署Flask应用：
https://www.jianshu.com/p/5b09394bebfe

Docker build 命令：
https://www.runoob.com/docker/docker-build-command.html

Windows部署Docker：
https://blog.csdn.net/paycho/article/details/127574796

docker中vim命令无法使用的那些事
https://blog.csdn.net/sinat_27915029/article/details/81148691

docker container run nginx ls -R -l /usr/share/nginx/html
curl http://127.0.0.1:8088

docker安装nginx静态文件服务器
https://blog.csdn.net/wugenqiang/article/details/86513257

docker部署nginx或httpd做图片静态资源
https://blog.csdn.net/qq_40907704/article/details/124697382

Docker配置nginx文件(图片)访问代理
https://blog.csdn.net/laok186/article/details/120263002

docker：创建nginx图片服务器
https://blog.csdn.net/textdemo123/article/details/100518122

挂载实现：docker容器里nginx访问宿主机文件
https://blog.csdn.net/qq_42162899/article/details/123813666

nginx服务器网站目录浏览,Nginx开启目录浏览功能 | 系统运维
https://blog.csdn.net/weixin_42099070/article/details/119510147

location / {
        root   /usr/share/nginx/html;
        index  index.html index.htm;
    }

location / images {
        alias   \myweb\images;
        autoindex on;
    }
git@code.17yund.me:ai/label_system_grpc_server.git
https://code.17yund.me/ai/label_system_grpc_server.git



apt-get update
apt-get install vim