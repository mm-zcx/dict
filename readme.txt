本项目是基于python3写的一个电子词典项目

    本项目使用到mysql数据库和python的pymysql模块，如果没有请安装
    本项目暂时只能在Linux下运行，没有图像界面，考虑以后会升级


dict.txt是一个词典文件，
dict_insert.py是把词典写入数据库程序
dict_server.py是字典的服务端程序
dict_cline.py是字典的客户端程序

使用本项目需要在服务端数据库中执行一下命令
    create database dict default charset=utf8;
    use dict;
    create table user (id int primary key auto_increment,name varchar(32) not null,passwd varchar(16) default '000000');
    create table hist(id int auto_increment primary key,name varchar(32) not null,word varchar(32) not null,time varchar(64));   
    create table words (id int auto_increment primary key,word varchar(32) not null,interpret text not null);

服务端程序使用：
	打开dict_server.py
	在 #创建数据库链接
	修改mysql的登录账户和密码
	退出保存
    直接在终端中启动就行
    python3 dict_server.py
    就启动成功

客户端程序使用：
    直接在终端中启动
	python3 dict_cline.py  你的服务器ip地址  端口号
	(默认端口号为8000)
