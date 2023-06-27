后台服务变成grpc_python2了，出错

发现nginx配置文件中代理的是grpc_python2，修改成label_python
配置此处用于获取客户端的真实IP
```nginx
proxy_set_header Host $http_host;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Proto $scheme;
proxy_pass http://label-system-backend-python:8080/;
#proxy_pass http://grpc_python2:8080/;# 注释掉grpc_python2
```


把grpc_python2，label-system-backend-python单独放入一个网络，grpc_python2只需要和python后端通信
```docker-compose.yml
networks:
     - label_system_default
     - network_grpc
     
networks:
      - network_grpc
      
networks:
  label_system_default:
  network_grpc:
```
没有给grpc_python2映射端口，

ip：grpc容器名，host：grpc服务端监听的端口
```python
def SayHello():
    with grpc.insecure_channel('{}:{}'.format('grpc_python2', '10053')) as channel:
    
```