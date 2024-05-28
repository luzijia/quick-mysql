### 名称：quick-mysql
### 简介：一键快速安装mysql，程序无序修改自动支持分库分表，完全透明。
### 安装说明：   
1. 编辑config.ini
2. 执行 ./quickmysql -i config.ini 进行安装
3. 删除 ./quickmysql -r config.ini 进行删除

#### 硬件要求
1. 操作系统：RHEL, CentOS,Ubuntu,macOS 10.13+
2. 软件：glibc 2.12+, x86_64, x86_32
3. 内存：最小1GB以上
4. 本地存储：最小1GB以上
5. 网络：最小百兆网卡

```javascript
[root@192 hamysql]# ./quickmysql -i config.ini
loading config OK
Extracting...
Setting environment variables...
Installing...
Install OK Thank You!
Testing Create Database and use table to insert
Table	Create Table
t1	CREATE TABLE `t1` (\n  `a` int(11) NOT NULL,\n  `b` int(11) DEFAULT NULL,\n  PRIMARY KEY (`a`)\n) ENGINE=SPIDER DEFAULT CHARSET=utf8mb4\n PARTITION BY LIST (crc32(`a`) MOD 1)\n(PARTITION `pt0` VALUES IN (0) COMMENT = 'database "test1_0", table "t1", server "SPT0"' ENGINE = SPIDER)
a	b
1	2
2	3
4	5
7	8
Testing OK
/root/hamysql
Script executed successfully.
Please Use /data/app/mysql/bin/mysql -umysql -pmysql -h192.168.1.7 -P3306 来访问数据库吧～
[root@192 hamysql]#  /data/app/mysql/bin/mysql -umysql -pmysql -h192.168.1.7 -P3306
Welcome to the MySQL monitor.  Commands end with ; or \g.
```
### 商务合作
#### 联系邮箱: luzijia@gmail.com
