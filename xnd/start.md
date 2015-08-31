##### 1.启动流程
1. 查找zk以前是否消费过,
    get /otter/canal/destinations/example/1001/cursor
    1)消费过:{"@type":"com.alibaba.otter.canal.protocol.position.LogPosition","identity":{"slaveId":-1,"sourceAddress":{"address":"172.16.82.174","port":3306}},"postion":{"included":false,"journalName":"mysql-bin.000004","position":48989,"timestamp":1440474349000}}
表示上次消费到了mysql-bin.000004文件的48989位置.
    2)
2. 发送COM_BINLOG_DUMP命令
    command:COM_BINLOG_DUMP with position:BinlogDumpCommandPacket[binlogPosition=48989,slaveServerId=1234,binlogFileName=mysql-bin.000004,command=18]
3.