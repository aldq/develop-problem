1. SHOW TABLES LIKE '%user%';

2. select TABLE_NAME from INFORMATION_SCHEMA.TABLES whereTABLE_SCHEMA=‘dbname’ and TABLE_NAME=‘tablename’ ;

3. 如果表不存在就建立这个表，那么可以直接用 create table if not exists tablename 这样的指令来建立，不需要先去查询表是否存在。

4. 从模板表创建表：create table if not exists like old_table_name;

5. 使用select * from tablename;如果表不存在则会报错
 