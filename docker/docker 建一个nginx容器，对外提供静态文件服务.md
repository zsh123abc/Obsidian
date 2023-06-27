
主机创建文件夹把nginx里的default.conf配置文件复制进来：
`C:\Users\cwj\myweb\nginx\conf.d\default.conf:/etc/nginx/conf.d/default.conf`
主机创建文件夹和nginx里的文件夹对应：
	`C:\Users\cwj\myweb\nginx\html:/usr/share/nginx/html/`

挂载主机文件到nginx里：
`docker run -p 80:80 --name nginx-zsh -v D:\zsh\nginx\conf.d\default.conf:/etc/nginx/conf.d/default.conf -v D:\zsh\nginx\html\:/usr/share/nginx/html/ -v D:\zsh\nginx\nginx.conf:/etc/nginx/nginx.conf -d nginx`

挂载主机和nginx的配置文件，修改主机文件，nginx文件也会修改
挂载主机存放静态文件目录和nginx存放静态文件目录。主机添加文件，nginx里也会添加文件

访问时：http://localhost:80/a.jpg
端口号后加文件名字



！！！想要实现文件浏览，必须要在nginx.conf里的http{}里和default.conf里的server{}里添加autoindex on
		docker nginx 把一个nginx.conf分成两个，
		（nginx.cong）和（default.conf）
		访问时：http://localhost:80/nginx


`docker run -p 8090:80 --name nginx-web4 -v C:\Users\cwj\myweb\nginx\conf.d\default.conf:/etc/nginx/conf.d/default.conf  -d nginx`


location = /50x.html {
        root   /usr/share/nginx/html;
    }

docker run --name nginx -d -p 80:80 -v D:/zsh/home:/home nginx