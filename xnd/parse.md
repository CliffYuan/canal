##### 解析流程
CanalEntry.Entry由3部分组成:
{
CanalEntry.Header,
CanalEntry.EntryType,
CanalEntry.ByteString
}

##### 1.阻塞接收数据
DirectLogFetcher.fetch0(){ channel.read(buffer);}没有数据时候,阻塞在止.

##### 2.接收到数据流程
1)
int netlen = getUint24(PACKET_LEN_OFFSET);//62
int netnum = getUint8(PACKET_SEQ_OFFSET);//5
TableMapLogEvent

TableMapLogEvent解析成CanalEntry.Entry==null

2)
int netlen = getUint24(PACKET_LEN_OFFSET);//52
int netnum = getUint8(PACKET_SEQ_OFFSET);//6
WriteRowsLogEvent

EntryType=ROWDATA

3)
XidLogEvent
EntryType=TRANSACTIONEND
会调用flush(),投递消息到eventStore中




##### insert操作binlog日志例子(innodb引擎)
以一条insert语句为例，包含4个事件：
1)TABLE_MAP_EVENT
2)QUERY_EVENT  (begin)  --事务开始
3)WRITE_ROWS_EVENT
4)XID_EVENT             --事务结束


##### PB对象之间的关系
Entry{
    Header,
    EntryType,//表示是事务标示还是数据
    Value;
}
Header{
    EventType,//insert,update等
    ....
}

RowChange{
    RowData,
    EventType
}

RowData{
    Column,
    Column,
}

message Column {
	name,
	value,
	iskey,
	updated
}

/**打散后的事件类型，主要用于标识事务的开始，变更数据，结束**/
enum EntryType{
	TRANSACTIONBEGIN 		=		1;
	ROWDATA					=		2;
	TRANSACTIONEND			=		3;
	/** 心跳类型，内部使用，外部暂不可见，可忽略 **/
	HEARTBEAT				=		4;
}

/** 事件类型 **/
enum EventType {
    INSERT 		= 		1;//插入
    UPDATE 		= 		2;//更新
    DELETE 		= 		3;//删除
    CREATE		= 		4;
    ALTER		= 		5;
    ERASE		= 		6;
    QUERY		=		7;
    TRUNCATE	=		8;
    RENAME 		= 		9;
    /**CREATE INDEX**/
    CINDEX		= 		10;
    DINDEX 		= 		11;
}

#### 解析body
LogDecoder.decode()解析







