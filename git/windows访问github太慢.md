
原因：github网站位置位于国外
每次访问需要经过dns解析域名，很麻烦，时间都浪费在路上了
解决：用域名解析网站查看github的ip，把ip：域名写进`C:\Windows\System32\drivers\etc\ hosts`中

`ipconfig /flushdns` 刷新 `dns` 缓存

查询到的 ip：
140.82.112.4 		github.com
199.232.69.194 		github.global.ssl.fastly.net
140.82.113.4 		gist.github.com
185.199.108.154		help.github.com
185.199.108.154		docs.github.com
185.199.109.153		desktop.github.com
34.201.80.84		vscode-auth.github.com
140.82.113.21		education.github.com
140.82.114.17		status.github.com

解决保存`C:\Windows\System32\drivers\etc\ hosts`文件没有权限：
https://blog.csdn.net/weixin_44295184/article/details/127513073

GitHub访问速度慢
https://blog.csdn.net/zjy1175044232/article/details/121655760