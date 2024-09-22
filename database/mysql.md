# MySQL Cheatsheet

## 连接管理
- 连接到MySQL: mysql -u [username] -p[password] -h [hostname] -P [port] -D [database]
- 退出MySQL: EXIT; 或 \q

## 用户管理
- 创建用户: CREATE USER 'username'@'host' IDENTIFIED BY 'password';
- 授予权限: GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'host';
- 撤销权限: REVOKE ALL PRIVILEGES ON database_name.* FROM 'username'@'host';
- 删除用户: DROP USER 'username'@'host';
- 修改用户密码: ALTER USER 'username'@'host' IDENTIFIED BY 'new_password';

## 数据库操作
- 显示所有数据库: SHOW DATABASES;
- 创建数据库: CREATE DATABASE database_name;
- 使用数据库: USE database_name;
- 删除数据库: DROP DATABASE database_name;

## 表操作
- 显示所有表: SHOW TABLES;
- 创建表: CREATE TABLE table_name (column1 datatype, column2 datatype, ...);
- 显示表结构: DESCRIBE table_name; 或 SHOW COLUMNS FROM table_name;
- 删除表: DROP TABLE table_name;
- 修改表: ALTER TABLE table_name ADD column_name datatype;
- 重命名表: RENAME TABLE old_name TO new_name;

## 数据操作
- 插入数据: INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
- 查询数据: SELECT column1, column2, ... FROM table_name WHERE condition;
- 更新数据: UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
- 删除数据: DELETE FROM table_name WHERE condition;

## 数据类型
- 整型：
  - INT: 4字节，范围 -2^31 到 2^31-1
  - BIGINT: 8字节，范围 -2^63 到 2^63-1
  - TINYINT: 1字节，范围 -128 到 127
  - SMALLINT: 2字节，范围 -32768 到 32767
  - MEDIUMINT: 3字节，范围 -8388608 到 8388607

- 浮点型：
  - FLOAT: 4字节，单精度浮点数
  - DOUBLE: 8字节，双精度浮点数
  - DECIMAL(M,D): 精确的小数值，M是总位数，D是小数位数

- 文本型：
  - CHAR(n): 固定长度字符串，最多255字符
  - VARCHAR(n): 可变长度字符串，最多65535字符
  - TEXT: 最大长度为65535字符
  - LONGTEXT: 最大长度为4294967295字符
  - ENUM: 枚举类型，最多65535个值

- 日期时间：
  - DATE: YYYY-MM-DD，范围 1000-01-01 到 9999-12-31
  - TIME: HH:MM:SS
  - DATETIME: YYYY-MM-DD HH:MM:SS
  - TIMESTAMP: YYYY-MM-DD HH:MM:SS，范围 1970-01-01 到 2038-01-19
  - YEAR: YYYY，范围 1901 到 2155

## 索引
- 创建索引: CREATE INDEX index_name ON table_name (column1, column2, ...);
- 删除索引: DROP INDEX index_name ON table_name;

## 事务
- 开始事务: START TRANSACTION;
- 提交事务: COMMIT;
- 回滚事务: ROLLBACK;

## 视图
- 创建视图: CREATE VIEW view_name AS SELECT column1, column2, ... FROM table_name WHERE condition;
- 删除视图: DROP VIEW view_name;

## 存储过程
- 创建存储过程: 
  DELIMITER //
  CREATE PROCEDURE procedure_name(IN parameter1 datatype, OUT parameter2 datatype)
  BEGIN
    -- SQL statements
  END //
  DELIMITER ;
- 调用存储过程: CALL procedure_name(param1, @param2);

## 备份和恢复
- 备份数据库: mysqldump -u [username] -p[password] database_name > backup.sql
- 恢复数据库: mysql -u [username] -p[password] database_name < backup.sql