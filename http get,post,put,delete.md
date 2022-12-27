get:
	第一种：直接在URL后面加参数：
		localhost:21811/Handler1.ashx?id=1&name=“abc”；
	
	第二种：用超链接的方法传递参数：当点击超链接的时候，首先会跳转：
		localhost:21811/Handler1.ashx页面，然后还会传递id 和name 两个参数过去；
	
	第三种：通过form表单传递：
		form action=“Handler1.ashx” method=“get”，注意action里面的连接不能带参数的；

post:
	1. url地址栏中传参
		以?分割URL和传输数据，参数之间以&相连，
		如：localhost:8080/user/?id=2&userName="王慢慢"&password="123655"
	2，作为send()的形参传递的

get  查，post 增，put 改，delete 删


四种请求方式 get、post、put、delete 的用法及区别：
https://blog.csdn.net/weixin_50001396/article/details/112969538
