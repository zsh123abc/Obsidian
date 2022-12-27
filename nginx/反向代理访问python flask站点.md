启动一个flask app.py
if __name__ == '__main__':
    app.run(host='0.0.0.0',port=8080)

 * Running on http://127.0.0.1:8080
 * Running on http://192.168.100.218:8080

default.conf配置：
location / {
       proxy_pass  http://192.168.100.218:8080;
    }

访问nginx的http://localhost:80时，跳转到flask的http://localhost:8080