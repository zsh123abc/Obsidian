docker-compose yml文件编写
command: nohup python3 /yd/ComputeServicer.py &

```
services:  #定义容器
		  mysql: 这个名字是用户自己自定义的，它就是服务名称
			    image: "mysql:5.7" #镜像来源，和build二选一
			    container_name: 自定义容器名
			    volumes: "/home/yd/label_system:/apps"指定数据挂载信息指定目录或文件的映射
			    #environment：添加环境变量，指定容器可选参数的值信息
			    ports: "8080:8080" 容器与宿主机的端口映射信息，格式为`宿主机端口:容器端口`
			    privileged: true 给予此容器扩展的特权
				shm_size: 2gb 为此构建的容器设置/dev/shm分区的大小，2gb或者1000000000
			    command: 覆盖容器启动后默认执行的命令
			    depends_on: 解决容器的依赖、启动先后的问题
```
依赖顺序，

	顺序不对，程序运行不了
	nginx不需要依赖grpc服务
 nginx:
    image: bitnami/nginx:1.20.2-debian-10-r128
    container_name: label_system_nginx
    ports:
      - '1080:8080'
      - '10443:443'
    volumes:
      - ./nginx_conf/vhost/label_system.conf:/opt/bitnami/nginx/conf/server_blocks/label_data.conf:ro
      - ./nginx_conf/certs:/certs
    networks:
      - label_system_default
    depends_on:
      - label-system-backend
      - label-system-backend-python
      - label-system-frontend