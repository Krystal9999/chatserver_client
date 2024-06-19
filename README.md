# chatserver
基于订阅-发布redis消息队列的nginx tcp负载均衡环境下在muduo网络库实现的集群聊天服务器和客户端代码

## 使用说明
第一步、启动Nginx,找到其路径位置并运行
	cd /usr/local/nginx			// 安装的默认路径位置
	./nginx
 sudo netstat -tanp				//观察nginx是否启动成功，默认TCP端口8000， HTTP端口88
第二步、启动Redis，找到其路径位置并运行
	cd /etc/redis						// redis文件夹中寻找redis.conf文件
	sudo redis-server redis.conf
 	sudo netstat -tanp			// 观察redis是否启动成功，默认端口6379
第三步、启动MYSQL
	mysql -u root -p 输入密码
  创建表，具体说明在https://blog.csdn.net/weixin_41987016/article/details/136007616
	sudo netstat -tanp 			//观察MYSQL是否启动成功
 
## 分别打开终端并输入可执行程序
	./ChatClient	127.0.0.1(ip号) 	8000(port) 
	./ChatServer	127.0.0.1(ip号) 	6000(port端口号) 

# 从头开始编译流程
	# 进入到build文件夹，编译产生的文件都放在这里
	cd build
  # 编译上级目录的CMakeLists.txt,生成makefile和其他文件
 	cmake ..
	# 执行make命令，在bin中就生成可执行文件
  make
	
