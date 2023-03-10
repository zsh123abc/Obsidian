构建多个关联的服务
	docker-compose命令
		在哪个目录下执行，就是对于该目录下的docker-compose.yml文件的操作



查看通过docker-compose运行了哪些容器:
cd到docker-compose.yml文件的目录
```
docker-compose ps 
```

-d后台运行compose
```
docker-compose up -d  
```