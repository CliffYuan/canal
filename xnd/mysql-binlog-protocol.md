##### COM_BINLOG_DUMP协议
body length(SequenceNumber) | COM_BINLOG_DUMP
4 | COM_BINLOG_DUMP数据包


##### mysql bin-log文件格式
1. 每个bin-log文件以fe 62 69 6e开头
    fe 62 69 6e -> .bin
2. bin-log 版本(Binlog Versions)
    Binlog version MySQL Version
    1 MySQL 3.23 - < 4.0.0
    2 MySQL 4.0.0 - 4.0.1
    3 MySQL 4.0.2 - < 5.0.0
    4 MySQL 5.0.0+
3.



##### 重点关注EventType

1.QUERY_EVENT
    binlog模式为statement的sql和ddl语句。

2.binlog模式为Row才有如下3中event
WRITE_ROWS_EVENT
UPDATE_ROWS_EVENT
DELETE_ROWS_EVENT
