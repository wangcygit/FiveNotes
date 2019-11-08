# **一、认识数据库：**

**1、常用的关键字**

数据库管理系统(DBMS DataBase Mangerment Sysytem)：

对不同的数据库进行统一的管理，提供统一的操作SQL语句的服务器软件。

数据库(database|schema)：存放数据的仓库。

数据表(table):数据表中存放具体的数据。

列(Column/cols) ：一列，在数据库中表示一个字段。

字段(Field)：字段往往指的是第一行所有的列。

行(Rows)：指的是字段以下真实、具体的数据。

记录(Record)：记录也叫行数据，也叫数据。

**2、常用的数据库有那些？**

MySQL 开源，有闭源的可能，被Oracle(甲骨文)公司收购。

Oracle 闭源，收费，Oracle公司。

SQL Server 微软公司。

DB2     IBM公司。

Access  微软公司。

高性能的数据库：

MogoDB  分布式数据库。

Memcache 内存缓存数据库。

Redis    k-v 键值对存储库，非关系型文档数据库。



# **二、MySQL数据库操作**

**1、MySQL数据库的安装**

官网 https://www.mysql.com/downloads/

安装教程见安装文档。

**2、 MySQL软件安装目录：**

目录：

C:\Program Files\MySQL\MySQL Server 5.7

核心文件夹：MySQL安装目录\bin(binary) 

**3、环境变量：**

**1)、什么是环境变量？**

环境变量是windows下根据安装的软件映射地址，多个地址要求以分号(;路径分隔符)分割。 

Linux 目录分隔符(/)

C:/king/images/hello.png 

Windows 目录分隔符(\)

C:\king\images/world.png 

举例：路径分割符(;)

C:\king\images/hello.png;C:\king\images/world.png 

**2)、环境变量在哪里？**

计算机--》右键 --》属性 --》高级系统设置

--》环境变量--》系统变量

**3)、怎么添加MySQL软件的环境变量？**

复制MySQL安装位置\bin目录所有在路径，添加到系统环境变量中的path后。

举例：xxxxxxx/xxxx/xxxx已经存在的路径;你的软件路径;

**注意：路径之间使用分号分割，不能误删已经存在的地址。**



# **三、MySQL数据库的登录和退出：**



**1、打开windows的终端：win+r 输入cmd 点回车。**

**2、启动MySQL服务**

桌面--》计算机 --》右键 --》管理 --》服务和应用程序 --》服务--》找到MySQL80-》右键 --》启动停止。

命令控制MySQL服务：

net start mysql80  启动

net stop mysql80   停止

注意：10061错误的解决办法。

**3、MySQL数据库的登录和退出**

登录语法： mysql [-h主机地址] -u用户名 -p密码 [-P端口号] 回车

例：mysq -u root -p 

退出： 

语法1：quit 回车

语法2：exit 回车

语法3：\q   回车



# **四、MySQL数据库的操作**

**1、MySQL SQL语句命令的语法规范：**

​	A、所有的命令和符号必须是英文状态。

​	B、所有的操作命令必须以分号(;)结尾。

​	C、所有输入的库名、数据表的名字、字段名字建议小写，

​	   所有数据库命令相关的关键字推荐纯大写。

​	D、使用数据库名、表名、字段名如果和数据库管理系统关键字

​	   冲突，必须使用反引号(`)转义。

**2、关于数据库的常用命令：**

help   				寻求命令帮助 

\G     				网格化显示结果

\c     				撤销正在执行的命令  

\T  D:/文件名.sql   开启记录日志，保存日志到指定的文件中 

\t                  结束日志保存

**3、数据库常用的函数：**

SELECT USER();      查看目前登录的用户名

SELECT VERSION();   查看系统版本号

SELECT NOW();       查看系统时间

**4、MySQL数据库的注释：**

注释：注释指用来对命令和操作步骤解释说明的文字。

语法：

\## 注释内容

-- 注释内容

**5、数据库(DATABASE)的操作：**

**1)、数据库的新建(CREATE):**

语法： 

CREATE DATABASE IF NOT EXISTS 数据库名 DEFAULT CHARSET = 'UTF8';

说明：创建数据库并指定编码方式。

**2)、查看系统中有那些数据库？**

SHOW DATABASES;

**3)、查看数据的详细信息(包含数据的编码方式)：**

SHOW CREATE DATABASE 数据库名;

**4)、打开(使用)数据库**

USE 数据库名;

**5)、查看当前正在使用的数据库。**

SELECT DATABASE();

**6)、删除数据库**

DROP DATABASE IF EXISTS 数据库名;



# **五、约束条件和数据类型(重点)**

**1、约束的意义：**

对数据库中字段对应的数据做合法的限定，保证数据的可靠性、安全性、减少冗余

**2、约束条件的分类：**

PRIMARY KEY     主键约束，用来修饰主键的。

AUTO_INCREMENT 	自增长约束，用来配合PRIMARY KEY修饰主键的，主键不需要加唯一约束。

UNIQUE KEY      唯一约束，用来规范字段值不能重复，NULL值不算。

NOT NULL        非空约束，用来规范字段值不能为空。

DEFAULT         "值"    默认值约束，给允许为空的字段添加默认的值。

COMMENT         "注释内容"  对字段进行解释说明。

**说明：**

​	**主键在一张表中有且只有一个，相当于一个excel表的序号。**

​	**主键必须是唯一的，往往是自动增长的。**

​	**主键是用来作为一行有效数据的唯一标识。**

​	**往往习惯把第一个字段设置为主键。**

​	**NULL是一种特殊类型，表示什么也没有。**



# **六、数据类型**



**1)、布尔型：**

**BOOLEAN  布尔型，用来存储true或者false的类型。**

**往往喜欢用TINYINT(1) 表示布尔，1表示true，0表示false。**

**2)、整型：**   

TINYINT(长度) 微整型，UNSIGNED 无符号位，ZEROFILL 零填充，占1个字节

有符号位的存储范围： -128 ~ 127 (-2^7 ~ 2^7 -1)

无符号位的存储范围：  0 ~ 255 (0 ~ 2^8 -1)

SMALLINT(长度) 小整型，UNSIGNED 无符号位，ZEROFILL 零填充，占2个字节

有符号位的存储范围： -32768 ~ 32767 (-2^15 ~ 2^15 -1)

无符号位的存储范围：  0 ~ 265535 (0 ~ 2^16 -1)

MEDIUMINT(长度) 中整型，UNSIGNED 无符号位，ZEROFILL 零填充，占3个字节

有符号位的存储范围： -8399608 ~ 8399607 (-2^23 ~ 2^23 -1)

无符号位的存储范围：  0 ~ 16777215 (0 ~ 2^24 -1)

INT(长度) 整型，UNSIGNED 无符号位，ZEROFILL 零填充，占4个字节

有符号位的存储范围： -2148483648 ~ 2148483647 (-2^31~ 2^31 -1)

无符号位的存储范围：  0 ~ 4296967295 (0 ~ 2^32 -1)

BIGINT(长度) 大整型，UNSIGNED 无符号位，ZEROFILL 零填充，占8个字节

有符号位的存储范围： -9223372036854775808 ~ 9223372036854775807 (-2^7 ~ 2^7 -1)

无符号位的存储范围：  0 ~ 18446744073709551615 (0 ~ 2^864-1)

 注意：常用TINYINT 、INT 、BIGINT。

​	    ZREOFILL零填充，给age TINYINT(3) ZEROFILL ，存储18，会显示成018。

​	    存储一个1，会显示001；

**3)、浮点型（小数）**

FLOAT(M,N) 	   UNSIGNED 无符号位，ZEROFILL 零填充,单精度浮点数。

DOUBLE(M,N)	   UNSIGNED 无符号位，ZEROFILL 零填充，双精度浮点数。

DECIMAL(M,N)   UNSIGNED 无符号位，ZEROFILL 零填充 ，定点型浮点，精度最高，不容易出现误差。

注意： M是数的总位数，M最大为65，默认为10；

​            N是小数点后的小数位数，最大为10，默认为0。

​	    常用是FlOAT。

**4)、字符串(String)：**	

CHAR(长度)  固定长度的字符串，定长，最长的宽度是255个字符，默认为1个。占用空间大，效率高。

VARCHAR(长度)  可变长度的字符串，变长。最大65535个，占用空间小，查询效率低。

TINYTEXT(长度)  最大长度 0~255个字符。

TEXT(长度)  	最大长度 0~65535个字符。

MEDIUMTEXT(长度)  最大长度 0~16777215个字符。

LONGTEXT(长度)  最大长度 0~4296967295个字符。

**注意:**

1. **必须记住CHAR和VARCHAR的区别。**
2. **常用的CHAR、VARCHAR、TEXT、LONGTEXT。**`

**5)、枚举型和集合**

枚举是一组有穷尽的、有相同意义的值，个数一定，多个选一个。

ENUM(值1,值2,...)   枚举型

集合是多个值的容器，最多提供64个选项，可以任意组合。

SET(值1,值2,...)  集合

举例： sex ENUM("男","女")  取值可以是男 或者 女。

​       option SET("A","B","C")  取值可以是A,B,AB...

注意：常用的是ENUM枚举型。

6)、时间日期类型：

YEAR 		年份类型。格式：YYYY ,比如：2019, "2018"

DATE 		日期类型。格式：YYYY-MM-DD ,比如：2019-12-05, "2018-05-18"

TIME 		时间类型。格式：HH:mm:SS,比如：14:24:36, "15:50:59"

DATETIME    时间日期类型。格式：YYYY-MM-DD HH:mm:SS, ,比如：2019-12-05 14:24:36, "2019-12-05 14:24:36"

TIMESTAMP  时间戳，表示从计算机元年1970年到2038年之间的秒数(对应的是日期时间)。

​		   一般给设置TIMESTAMP类型的字段设置默认值为 CURRENT_TIMESTAMP();

​		   取值可以是秒数、时间值、日期时间值。

注意： 常用的是DATE，DATETIME、TIMESTAMP类型。

扩展：

​	SELECT CURRENT_TIME();  		-- 获取当前的时间

​	SELECT CURRENT_DATE();  		-- 获取当前的日期

​	SELECT CURRENT_TIMESTAMP();  	-- 获取当前的时间戳



# **七、数据表TABLE的操作(重点)**



**1、创建数据表**

语法：

CREATE TABLE IF NOT EXISTS 数据表名(

​	字段1 数据类型(长度) 约束条件1 约束条件2... 注释,

​	字段2 数据类型(长度) 约束条件1 约束条件2... 注释,

​	...

​	字段n 数据类型(长度) 约束条件1 约束条件2... 注释

)[ENGINE = INNODB AUTO_INCREMENT = 值  DEFAULT CHARSET = 'utf8'];

注意：最后一个字段省略逗号(,);

**2、查看有哪些数据表？**

SHOW TABLES;（查询有那些数据表需在TABLE后加S）

**3、查看表的详细信息**

查看数据表的信息(包含编码方式)

SHOW CREATE TABLE 数据表名;   

查看数据表的结构信息(包含的字段信息)

DESC 数据表名;

DESCRIBE  数据表名;

查看数据表的字段信息(包括字段的注释、权限)

SHOW FULL COLUMNS FROM 数据表名;



# 八、 数据表结构(ALTER)



1、字段的添加(ALTER  ADD)：

1)、添加一个字段：

ALTER TABLE 数据表名 

ADD [COLUMN] 字段名  数据类型 约束条件  [FIRST|AFTER 字段名];

注意：[] 表示可以省略，|表示或者。

2)、添加多个字段：

ALTER TABLE 数据表名 

​	ADD [COLUMN] 字段名1 数据类型 约束条件 [FIRST|AFTER 字段名],

​	ADD [COLUMN] 字段名2 数据类型 约束条件 [FIRST|AFTER 字段名],

​	...

​	ADD [COLUMN] 字段名n 数据类型 约束条件 [FIRST|AFTER 字段名];

2、字段的删除(ALTER  DROP)

A、删除单个字段

ALTER TABLE 数据表名 DROP [COLUMN] 字段名;

B、删除多个字段

ALTER TABLE 数据表名 

​	DROP [COLUMN] 字段名1,

​	DROP [COLUMN] 字段名2

​	...,

​	DROP [COLUMN] 字段名n;

3、修改字段的类型：(ALTER MODIFY)

ALTER TABLE 数据表名 MODIFY [COLUMN] 字段名 数据类型 约束条件 [FIRST | AFTER 字段名];

注意：主键约束的字段修改类型不需要再次给PRIMARY KEY。

​	   AUTO_INCREMENT约束需要正常给。

4、添加|删除自增长(同ALTER MODIFY)

1)、添加自增长

ALTER TABLE 数据表名 MODIFY [COLUMN] 字段名 数据类型

AUTO_INCREMENT 约束条件 [FIRST | AFTER 字段名];

注意：AUTO_INCREMENT 作用是配合PRIMARY KEY对主键字段做修饰的。

​	  所以给字段添加自增长，需要先把该字段变为主键。

2)、删除自增长

删除自增长约束和MODIFY语句相同，不写AUTO_INCREMENT即删除。

5、添加|删除主键(ALTER ADD|DROP)

1)、给字段添加主键

ALTER TABLE 数据表名字 ADD PRIMARY KEY(字段名); 

2)、给表删除主键

ALTER TABLE 数据表名字 DROP PRIMARY KEY; 

注意：在删除主键之前必须删除自增长约束。

6、修改字段的数据类型包括字段的名字(ALTER CHANGE)

ALTER TABLE 数据表名 CHANGE [COLUMN] 旧字段名 新字段名 数据类型 约束条件 [FIRST | AFTER 字段名];

7、更改数据表的名字(ALTER RENAME)：

ALTER TABLE 数据表名 RENAME TO  新名字;



# **九，数据表结构的修改**



## **1、为字段添加|删除唯一约束**

添加唯一约束

ALTER TABLE 数据表名  ADD [CONSTRAINT 唯一约束名]  UNIQUE KEY(字段名); 

--  给student表中的name字段添加唯一约束

ALTER TABLE student ADD UNIQUE KEY(name);

删除唯一约束

ALTER TABLE 数据表名  DROP INDEX 唯一索引名;

ALTER TABLE student DROP INDEX name;

注意：添加的唯一约束(索引)会自动生成一个名字。

​	  删除必须通过这个名字删除。

  	  唯一索引名不指定一般是字段名;

​	  如果字段的值有重复值，给该字段添加唯一约束会报错。

## **2、为字段添加|删除默认值约束(双ALTER语句)**

**A、添加默认值**

ALTER TABLE 数据表名 ALTER COLUMN 字段名 SET DEFAULT 值;

ALTER TABLE student ALTER COLUMN name  SET DEFAULT "无名";  

**B、删除默认值**

ALTER TABLE 数据表名 ALTER COLUMN 字段名 DROP DEFAULT;

-- 删除student表中的name字段的默认值

ALTER TABLE student ALTER COLUMN name DROP DEFAULT;



# **十，数据的添加(INSERT)：**



**1、添加一条数据**

INSERT INTO 表名(字段1,字段2...字段n)  VALUES(

值1,值2,...值n);

INSERT INTO 表名 SET 字段名1=字段值1,字段名2=字段值2,... 

字段名n=字段值n;

INSERT INTO 表名 VALUES(null,值1,值2,...值n); 

**2、一次添加多条数据：**

INSERT INTO 表名(字段1,字段2...字段n)  VALUES

(值1,值2,...值n),

(值1,值2,...值n),

...

(值1,值2,...值n);



INSERT INTO 表名 VALUES

(null,值1,值2,...值n), 

(null,值1,值2,...值n),

.... 

(null,值1,值2,...值n); 

**注意：**

​	 **1)、省略字段名的字段个数必须和字段值的个数一致。**

​	 **2)、字段必须按照数据表中的字段顺序。**

​	 **3)、主键一般给NULL或者DEFAULT。**

​         **4)、有默认值的字段一般给DEFAULT，建议不要给NULL。**



# **十一，数据的删除(DELETE)**



**1、删除全部的记录：**

DELETE FROM 数据表名; 

例：DELETE FROM commodity;        删除表commodity中的全部数据 

**2、截断表(删除全部的记录)**

TRUNCATE TABLE 数据表名;

例： -- 使用截断表删除xdl_studentinfo全部的数据 TRUNCATE TABLE xdl_studentinfo; 

**注意：一般不要删除全部的记录。**

​	  **DELETE删除记录不会清空主键的自增长值。**

​	  **截断表会删除所有记录，并清空自增长值。**

​	  **删除全部记录使用截断表效率高。**



# **十二、 WHERE条件**



**1、算术运算符条件**



\+  -  *  /(取商)  % (取模,取余,求余数) 



**说明：% 取模往往用来判断整数中的奇偶数。**

​	  **与2取模为零的数是偶数,与2取模不等于零的数是奇数。**



**2、比较关系条件**



<   小于    >    大于    <=    小于等于    >=   大于等于   <> (不等于)      != 不等于     = 等于

```mysql
-- 删除指定条件的记录,删除id为9的一条数据。
DELETE FROM xdl_studentinfo WHERE id = 9;

-- 删除偶数行记录
DELETE FROM xdl_studentinfo WHERE id % 2 = 0;

-- 删除性别不是女生的。
DELETE FROM xdl_studentinfo WHERE sex <> "女";
DELETE FROM xdl_studentinfo WHERE sex != "女";
```

**3、逻辑关系条件(或且非)**

OR 两个以上的条件或者的关系，满足一种即可。

AND 两个以上的条件是并列的关系，必须同时满足。

NOT 条件取反。

```mysql
-- 删除未成年并且性别是女生的记录
DELETE FROM xdl_studentinfo WHERE age <= 18 AND sex = "女";

-- 删除姓名叫彭于晏或者高圆园
DELETE FROM xdl_studentinfo WHERE name = "彭于晏"
OR name = "高圆圆";

-- 删除姓名叫赵丽颖并且叫王力宏
DELETE FROM xdl_studentinfo WHERE name = "王力宏"
AND name = "赵丽颖";
```





**4、限制范围的条件**



字段的值在列举的范围内条件成立： 字段名 [NOT] IN (值1,值2,...)       



字段的值在小值到大值之间条件成立：

字段名 [NOT] BETWEEN  小值 AND 大值;



**5、检测NULL值**



字段名 IS NULL 

字段名 IS NOT NULL 



**6、区分大小写的条件匹配：**



BINARY 字段名 = 值; 



```mysql
-- 删除id为5 选修课程为java的人 DELETE FROM xdl_studentinfo WHERE BINARY course = "java" AND id = 5; 
```

**注意：MySQL中条件匹配默认忽略大小写，如果要使用严格匹配大小写则使用BINARY;**



**7、模糊查询**



字段 [NOT] LIKE 通配符;



通配符的组成： 普通字符串、_、%。



```mysql
-- 删除姓王的人
DELETE FROM xdl_studentinfo WHERE name 
LIKE "王%";

-- 删除名字第二字是文的人
DELETE FROM xdl_studentinfo WHERE name 
LIKE "_文%";

-- 删除姓名中含有晏字的人
DELETE FROM xdl_studentinfo WHERE name 
LIKE "%晏%";

-- 删除姓名为两个字的人
DELETE FROM xdl_studentinfo WHERE name 
LIKE "__";
```

**注意：**

​	**1个_表示 1个任意的字符。**

​	**1个 %表示 任意多个任意字符。**



# **十三、带有WHERE条件的DELETE语句。**



**1、MySQL的特殊语法，不USE库直接操作表**

语法1： 库名.表名

语法2： 表名.字段名

**2、带有WHERE条件的DELETE语句：**

DELETE FROM 表名 WHERE 条件;

```mysql
-- 删除姓名为两个字的人
DELETE FROM xdl_studentinfo WHERE name 
LIKE "__";
```



# **十四、数据的更新UPDATE语句。**



**1、修改全部的记录**

UPDATE 表名 SET 字段名1=字段值1,字段名2=字段值2,...;

```mysql
-- 把表中孙红雷的年龄修改为34岁
UPDATE xdl_studentinfo SET age = 34 WHERE 
name = "孙红雷";
```



**2、修改指定条件的记录**

UPDATE 表名 SET 字段名1=字段值1,字段名2=字段值2,... WHERE 条件;

```mysql
-- 把表中孙红雷的年龄+5
UPDATE xdl_studentinfo SET age = age + 5 WHERE 
name = "孙红雷";
```



# **十五、数据的查询SELECT语句WGHOL;**



**1、查询所有字段所有记录(数据)**

SELECT * FROM 表名;

```mysql
-- 查询所有记录
SELECT * FROM xdl_studentinfo;
```



**2、查询所有字段中符合指定条件的记录;**

SELECT * FROM 表名 WHERE 条件;



**3、查询指定字段中符合指定条件的记录;**

SELECT 字段名1,字段名2,... FROM 表名 WHERE 条件;



```mysql
-- 查看薪水在5000以上的数据
SELECT salary AS "薪水" FROM xdl_studentinfo WHERE salary >= 5000;
```



**4、分组查询GROUP BY 字段名;**

SELECT 字段名1,字段名2,... FROM 表名 WHERE 条件 GROUP BY 字段名 ;

```mysql
-- 查询xdl_studentinfo表中的所有记录，按照性别分组
SELECT sex AS 性别 FROM xdl_studentinfo WHERE id >= 1 GROUP BY sex;

-- 查询xdl_studentinfo表中的所有记录，按照选课程分组
SELECT course AS 课程 FROM xdl_studentinfo WHERE id >= 1 GROUP BY course;
```



**5、HAVING 子句对分组的结果进行二次筛选。**

SEELCT 字段名1,字段名2,... FROM 表名 WHERE 条件 GROUP BY 字段名 HAVING 聚合函数;



```mysql
-- 统计出相同性别中人数大于6人的性别是男还是女？
SELECT sex AS 性别 FROM xdl_studentinfo 
GROUP BY sex HAVING COUNT(id) > 6;
```

**注意：HAVING子句需要配合聚合函数对分组查询的结果进行二次筛选。**



**6，聚合函数：**

​	COUNT(字段名)  计数

​	MAX(字段名)  最大值

​	MIN(字段名)  最小值

​	AVG(字段名)  平均值

​	SUM(字段名)  求和



```mysql
-- 查询表中所有年龄的总和是多少？SUM 
SELECT SUM(age) AS 总年龄 FROM  xdl_studentinfo;

-- 查询表中最大年龄、最小年龄分别是多少MAX MIN
SELECT MAX(age) AS 最大年龄,MIN(age) AS 最小年龄
FROM xdl_studentinfo;

-- 计算出表中平均年龄为多少岁？AVG
SELECT AVG(age) AS 平均年龄 FROM xdl_studentinfo;

-- 统计xdl_studentinfo表中一共有多少人
SELECT COUNT(id) AS 总人数 FROM xdl_studentinfo;
SELECT COUNT(*) AS 总人数 FROM xdl_studentinfo;
SELECT COUNT(name) AS 总人数 FROM xdl_studentinfo;
SELECT COUNT(age) AS 总人数 FROM xdl_studentinfo;
```



**说明：A、 AS可以给字段、表名取别名。**

​	  **B、 表名取别名以后，字段必须按照 表名.字段名的形式书写。**



练习：默写INSERT语句/DELETE语句/UPDATE语句/SELECT语句。

```mysql
INSERT INTO student (name,sex,aeg,tel) VALUES ("胡歌","男",36,17612117060);
INSERT INTO student VALUES (null,"胡歌"，"男",36,17612117060);

DELETE FROM student;
DELETE FROM student WHERE id = 9;

UPDATE student SET age = age + 5 WHERE name = "胡歌";
UPDATE student SET age = 34 WHERE name = "胡歌";

SELECT * FROM student;
SELECT name,age,tel FROM student;
SELECT salary AS "薪水" FROM student WHERE salary >= 5000;
SELECT name,sex,salary,address FROM student WHERE age BETWEEN 18 AND 60;
```



练习：熟悉各种WHERE语句,使用xdl_studentinfo表练习更新语句、查询语句。

```mysql
-- 查看xdl_studentinfo表中姓王的人
SELECT name,sex,age,address FROM xdl_studentinfo WHERE name LIKE "王%";

SELECT name,course,address,tel FROM xdl_studentinfo 
WHERE course = "PHP" OR course = "Java" ;

-- 查询xdl_studentinfo表中的所有记录，按照性别分组
SELECT sex AS 性别 FROM xdl_studentinfo WHERE id >= 1 GROUP BY sex;

-- 查询表中成年的男生 人数是多少？
SELECT COUNT(id) FROM xdl_studentinfo WHERE sex = "男" AND age >= 18;
```



# **十六、查询语句(SELECT)**



**1、排序 ORDER BY** 

​	SELECT 字段列表 FROM 表名 WHERE 条件 GROUP BY 字段

​	HAVING 聚合函数条件 ORDER BY 字段名 DESC降序 | ASC 升序;

**说明：**

​	**ASC是升序，排序字段从小到大。**

​	**DESC是降序，排序字段从大到小。**

​	**ORDER BY语句不加DESC或者ASC默认对字段进行升序排列。**

​	**ORDER BY语句支持同时给多个字段排序。**



**2、LIMIT 子句;**

**1)、LIMIT的语法：**

​	SELECT 字段列表 FROM 表名 WHERE 条件

​	GROUP BY 字段名 HAVING 聚合函数条件 ORDER BY 字段1 ASC| DESC ,字段2 ASC|DESC  LIMIT 偏移量,显示条数;

​	**举例：**

​	**显示指定的条数：**

​	**SELECT 字段列表 FROM 表名 LIMIT 显示条数;**

​	**从第几条后显示指定的条数：**

​	**SELECT 字段列表 FROM 表名 LIMIT 偏移量,显示条数。**

​	**说明：LIMIT 偏移量,显示条数往往用于分页，需要使用分页公式。**



**2)、分页公式(偏移量和总页数)：**

​	偏移量公式的推理过程：求第五页的偏移量是多少？

​	第1页 偏移量0  显示条数2

​	第2页 偏移量2  显示条数2

​	第3页 偏移量4  显示条数2

​	...

​	第5页 偏移量?  显示条数2       求偏移量是多少？ 2 * (5-1) = 8 

​	第8页 偏移量?  显示条数2       求偏移量是多少？ 2 * (8-1) = 16 

​	偏移量 =  (当前页码数 - 1) * 每页显示的记录数;

​	总页数 =  总记录数 / 每页显示的记录数;



**注意：总记录数除以每页显示的记录数需要向上取整。**

​	   **百度搜索的结果每页显示10条数+5条广告，百度也是按这个公式做的分页。**



**3)、LIMIT语句的特殊用法：**



​	删除前面的几个条：

​	DELETE FROM 表名 LIMIT 条数;

​	删除后面的几个条：

​	DELETE FROM 表名 ORDER BY 字段 ASC LIMIT 条数;

​	更新前面的几个条：

​	UPDATE 表名 SET 字段名1=字段值1,字段名2=字段值2,... LIMIT 条数;

​	更新后面的几个条：

​	UPDATE 表名 SET 字段名1=字段值1,字段名2=字段值2,...   ORDER BY 字段 DESC LIMIT 条数;

**总结：SELECT语句中出现的子句需要按照WGHOL的顺序。**



**3、常用的函数;**  



​	SELECT CEIL(数);  				向上取整

​	SELECT FLOOR(数);  			   向上取整

​	SELECT SQRT(数);  			     开平方根

​	SELECT ROUND();   			    0~1之间的随机数

​	SELECT POWER(底数,指数); 	      求幂运算

​	SELECT ABS(数);             	             绝对值

​	SELECT PI();             	 	            π

​	SELECT TRUNCATE(小数,位数);         截取指定的小数位

​	SELECT LOWER(字符串);   		 把指定的字符串变为小写

​	SELECT UPPER(字符串);   		  把指定的字符串变为大写



# **十七、连接查询**



**1、内连接查询INNER JOIN**

​	语法：

​	**1)、两张表的内连接查询:**

​		SELECT 字段列表 FROM 表1 [INNER] JOIN 表2 

​		ON 表1.字段名 = 表2.字段名;

​	**2)、多表的内连接查询：**

​		SELECT 字段列表 FROM 表1 

​		[INNER] JOIN 表2 

​		ON 表1.字段名 = 表2.字段名

​		[INNER] JOIN 表3 

​		ON 表2.字段名 = 表3.字段名

​		...

​		[INNER] JOIN 表n 

​		ON 表n-1.字段名 = 表n.字段名;

**注意：**

​	**内连接查询要求两张以上的数据表具有相同意义的字段，往往这两个字段的数据类型一致。**

​	**内连接查询得到的结果集是两张以上的表符合连接条件的交集部分。**

**2、外连接查询OUTER JOIN**

语法： 

​	1)、左外连接查询：

​		SELECT 字段列表 FROM 表1 

​		LEFT OUTER JOIN 表2

​		ON 表1.字段名 = 表2.字段名;

​	2)、右外连接查询：

​		SELECT 字段列表 FROM 表1 

​		RIGHT OUTER JOIN 表2

​		ON 表1.字段名 = 表2.字段名;

**注意：**

​	**外连接查询要求两张以上的数据表具有相同意义	的字段，往往这两个字段的数据类型一致。**

​	**左外连接查询得到的结果集是左表的全部，加上符合连接条件的**



# **十八、UNION关键字：**



UNION用于合并多条SELECT语句得到的结果集。

SELECT 语句1 UNION SELECT 语句2;



注意：

使用UNION合并的结果集查询语句中

要求具备显示相同的字段个数。



# 十九、增删改查四大语句



CURD增删改查(CREATE/UPDATE/READ/DELETE) 4大语句。

INSERT INTO 表名(字段名1,字段名2,...) VALUES(值1,值2,...);

INSERT INTO 表名(字段名1,字段名2,...) VALUES(值1,值2,...),

(值1,值2,...),

...

(值1,值2,...);

INSERT INTO 表名 VALUES(NULL,值1,值2,...);

INSERT INTO 表名 VALUES(NULL,值1,值2,...),

(NULL,值1,值2,...),

...

(NULL,值1,值2,...);

INSERT INTO 表名 SET 字段名1=字段值1,字段名2=字段值2,...;

DELETE FROM 表名 WHERE 条件;

UPDATE 表名 SET  字段名1=字段值1,字段名2=字段值2,... WHERE 条件;

SELECT 字段列表 FROM 表名 

WHERE条件 GROUP BY 字段名 HAVING 聚合函数条件 ORDER BY 字段名 ASC|DESC LIMIT 偏移量,显示的条数;