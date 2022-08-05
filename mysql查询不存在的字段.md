# 查询结果中增加数据库不存在的字段

MySQL增加不存在字段默认值

select a,b,c,'null' as d from table

增加字段d 默认值为null