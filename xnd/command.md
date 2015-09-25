
##### binlog相关的一些命令
1. show binlog events in 'master-bin.000007';
非常好用,详细展示了每个events事件.

mysql> show binlog events in 'mysql-bin.000001';
+------------------+-----+-------------+-----------+-------------+---------------------------------------+
| Log_name         | Pos | Event_type  | Server_id | End_log_pos | Info                                  |
+------------------+-----+-------------+-----------+-------------+---------------------------------------+
| mysql-bin.000001 |   4 | Format_desc |         1 |         107 | Server ver: 5.5.45-log, Binlog ver: 4 |
| mysql-bin.000001 | 107 | Stop        |         1 |         126 |                                       |
+------------------+-----+-------------+-----------+-------------+---------------------------------------+
2 rows in set (0.00 sec)

mysql> show binlog events in 'mysql-bin.000002';
+------------------+-----+-------------+-----------+-------------+---------------------------------------------------------------------------+
| Log_name         | Pos | Event_type  | Server_id | End_log_pos | Info                                                                      |
+------------------+-----+-------------+-----------+-------------+---------------------------------------------------------------------------+
| mysql-bin.000002 |   4 | Format_desc |         1 |         107 | Server ver: 5.5.45-log, Binlog ver: 4                                     |
| mysql-bin.000002 | 107 | Query       |         1 |         205 | CREATE USER canal IDENTIFIED BY 'canal'                                   |
| mysql-bin.000002 | 205 | Query       |         1 |         353 | GRANT SELECT, REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'canal'@'%' |
| mysql-bin.000002 | 353 | Query       |         1 |         428 | FLUSH PRIVILEGES                                                          |
| mysql-bin.000002 | 428 | Query       |         1 |         497 | BEGIN                                                                     |
| mysql-bin.000002 | 497 | Table_map   |         1 |         659 | table_id: 2 (mysql.user)                                                  |
| mysql-bin.000002 | 659 | Delete_rows |         1 |         836 | table_id: 2 flags: STMT_END_F                                             |
| mysql-bin.000002 | 836 | Query       |         1 |         906 | COMMIT                                                                    |
| mysql-bin.000002 | 906 | Stop        |         1 |         925 |                                                                           |
+------------------+-----+-------------+-----------+-------------+---------------------------------------------------------------------------+
9 rows in set (0.00 sec)

mysql> show binlog events in 'mysql-bin.000003';
+------------------+------+-------------+-----------+-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Log_name         | Pos  | Event_type  | Server_id | End_log_pos | Info                                                                                                                                                                                   |
+------------------+------+-------------+-----------+-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| mysql-bin.000003 |    4 | Format_desc |         3 |         107 | Server ver: 5.5.45-log, Binlog ver: 4                                                                                                                                                  |
| mysql-bin.000003 |  107 | Query       |         3 |         200 | create database meizu_sms                                                                                                                                                              |
| mysql-bin.000003 |  200 | Query       |         3 |         433 | use `meizu_sms`; create table T_SMS_USER(
                                                                        FID int(11) not null,
                                                                        FUSER_NAME varchar(20) not null,
                                                                        FPASSWORD varchar(45) not null,
                                                                        PRIMARY KEY (FID)
                                                                        )ENGINE=InnoDB DEFAULT CHARSET=utf8 |
| mysql-bin.000003 |  433 | Query       |         3 |         506 | BEGIN                                                                                                                                                                                  |
| mysql-bin.000003 |  506 | Table_map   |         3 |         566 | table_id: 33 (meizu_sms.T_SMS_USER)                                                                                                                                                    |
| mysql-bin.000003 |  566 | Write_rows  |         3 |         607 | table_id: 33 flags: STMT_END_F                                                                                                                                                         |
| mysql-bin.000003 |  607 | Xid         |         3 |         634 | COMMIT /* xid=111 */                                                                                                                                                                   |
| mysql-bin.000003 |  634 | Query       |         3 |         707 | BEGIN                                                                                                                                                                                  |
| mysql-bin.000003 |  707 | Table_map   |         3 |         767 | table_id: 33 (meizu_sms.T_SMS_USER)                                                                                                                                                    |
| mysql-bin.000003 |  767 | Write_rows  |         3 |         808 | table_id: 33 flags: STMT_END_F                                                                                                                                                         |
| mysql-bin.000003 |  808 | Xid         |         3 |         835 | COMMIT /* xid=164 */                                                                                                                                                                   |
| mysql-bin.000003 |  835 | Query       |         3 |         908 | BEGIN                                                                                                                                                                                  |
| mysql-bin.000003 |  908 | Table_map   |         3 |         968 | table_id: 33 (meizu_sms.T_SMS_USER)                                                                                                                                                    |
| mysql-bin.000003 |  968 | Write_rows  |         3 |        1012 | table_id: 33 flags: STMT_END_F                                                                                                                                                         |
| mysql-bin.000003 | 1012 | Xid         |         3 |        1039 | COMMIT /* xid=188 */                                                                                                                                                                   |
| mysql-bin.000003 | 1039 | Stop        |         3 |        1058 |                                                                                                                                                                                        |
+------------------+------+-------------+-----------+-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
16 rows in set (0.00 sec)

2. 查看当前binlog_format;
mysql> show variables like 'binlog_format';
+---------------+-------+
| Variable_name | Value |
+---------------+-------+
| binlog_format | ROW   |
+---------------+-------+


3.设置当前连接的binlog_format格式

set session binlog_format=mixed;

