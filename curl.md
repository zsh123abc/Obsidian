curl：模拟客户端发送请求到接口

1，windows系统安装curl：
https://blog.csdn.net/weixin_44360092/article/details/123670304

2，选中请求，复制值>复制为cURL命令(windows)

命名：
--output 107.xml

3，命令行执行复制到的curl命令

curl -H "Host: admin-brain.17yund.com" -H "User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0" -H "Accept: application/json, text/plain, */*" -H "Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2" -H "Content-Type: application/json;charset=utf-8" -H "Authorization: Bearer b4T0hQV5+OOu7ABM6utLigG5QvTkTfiTdhQ6uGDLHk0zKGYbUZm2tc/ZKx0FH7pX2/4JNK8ueZFK5tabvYQ9ugk81PamieS722Svs4xAdHjcAriPZhBMOYTc7F6x+ZWa7uM/URkJU1GFRNHakQsq0A==" -H "Origin: http://admin-brain.17yund.com" -H "Cookie: Admin-Token=b4T0hQV5+OOu7ABM6utLigG5QvTkTfiTdhQ6uGDLHk0zKGYbUZm2tc/ZKx0FH7pX2/4JNK8ueZFK5tabvYQ9ugk81PamieS722Svs4xAdHjcAriPZhBMOYTc7F6x+ZWa7uM/URkJU1GFRNHakQsq0A==; sidebarStatus=0" --data-binary "{\"userId\":137,\"familyMemberId\":516,\"beginAt\":\"580\",\"endAt\":\"2080\",\"labelId\":\"5\",\"logDataId\":3383}" --compressed "http://admin-brain.17yund.com/api/brain/data/logLabels/add"



https://curl.iculture.cc/