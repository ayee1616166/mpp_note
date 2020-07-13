[toc]

# 参考
https://blog.csdn.net/kk185800961/article/details/79378313/ <br />
http://blog.chinaunix.net/uid-26253010-id-4039457.html <br />
http://www.linuxyw.com/linux/shujuku/20130506/216.html <br />

# /etc/my.cnf
```	
[mysql]
auto-rehash                          # 自动补全命令
default-character-set=utf8           # mysql连接字符集
	
[client]
port=3367
default-character-set=utf8           # 设定客户端连接字符集
	
[mysqld]
lower_case_table_names=1             # 是用来配置数据库名和表名的大小写的。1表示不区分大小写，0表示区分大小写
character_set_server=utf8
init_connect='SET NAMES utf8'        # 用户登录到数据库上之后，在执行第一次查询之前执行 里面的内容的
init_connect='SET collation_connection = utf8_unicode_ci'
port=3367                            # 默认端口
##innodb_buffer_pool_size = 128M     # 用于缓存 索引 和 数据的内存大小
join_buffer_size = 128M              # mysql在内部处理多表join的方法是嵌套循环（nested_loop）,引入join_buffer的目的是减少嵌套循环外层的取数据的次数，提升查询性能
	
	
sort_buffer_size = 2M                # 是一个connection级参数，在每个connection（session）第一次需要使用这个buffer的时候，一次性分配设置的内存
	
read_rnd_buffer_size = 2M            # 是MySQL的随机读缓冲区大小
#basedir=/home/data/mysql            # 定义MySQL存放位置
datadir=/mysql/data                  # 设定数据存放位置
socket=/mysql/data/mysql.sock
                                
#设定服务端字符集
collation-server=utf8_unicode_ci
skip-character-set-client-handshake  # 跳过mysql程序起动时的字符参数设置 ，使用服务器端字符集设置
	
#symbolic-links=0
#sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES 
	
[mysqld_safe]                     
log-error=/mysql/data/mysqld.log
pid-file=/mysql/data/mysqld.pid      # 建议跟数据存放路径 
```

