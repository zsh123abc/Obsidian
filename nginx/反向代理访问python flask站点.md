启动一个flask app.py
if __name__ == '__main__':
    app.run(host='0.0.0.0',port=8080)

 * Running on http://127.0.0.1:8080
 * Running on http://192.168.100.218:8080


default.conf配置：
location / {
       proxy_pass  http://192.168.100.218:8080;
    }

proxy_pass参数后面绝对不能使用localhost或者127.0.0.1，必须使用宿主机当前实际使用的IP

查看本机ip信息：ipconfig/all

访问nginx的http://localhost:80时，跳转到flask的http://localhost:8080



Docker容器下部署Nginx反向代理报错的问题：

upstream server temporarily disabled while connecting to upstream
连接到上游时临时禁用上游服务器

https://blog.csdn.net/weixin_43260887/article/details/105403391